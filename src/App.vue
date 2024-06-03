<template>
  <div
    class="app-container"
    style="
      background-image: url('https://img.freepik.com/free-vector/futuristic-background-design_23-2148503793.jpg?size=626&ext=jpg&ga=GA1.1.672697106.1717372800&semt=ais_user');
      background-size: cover;
      background-position: center;
      background-repeat: no-repeat;
      height: 100vh;
      width: 100vw;
      position: fixed;
      top: 0;
      left: 0;
      overflow: auto; /* Menambahkan scroll jika konten melebihi tinggi layar */
    "
  >
    <div class="content-container">
      <form @submit.prevent="save" class="form-container">
        <label for="title">Masukin Judul:</label>
        <!-- Teks label untuk input judul -->
        <input
          type="text"
          id="title"
          v-model="form.title"
          class="input-title"
        /><br />
        <label for="content">Masukin Content:</label>
        <!-- Teks label untuk textarea content -->
        <textarea
          id="content"
          v-model="form.content"
          class="textarea-content"
        ></textarea
        ><br />
        <button type="submit" class="button-save">Save</button>
      </form>
      <ul class="articles-list">
        <li v-for="article in articles" :key="article.id" class="article-item">
          <div class="article-title">{{ article.title }}</div>
          <br />
          <div class="article-content">{{ article.content }}</div>
          <br />
          <button @click="edit(article)" class="button-edit">Edit</button>
          <button @click="deleteArticle(article)" class="button-delete">
            Delete
          </button>
        </li>
      </ul>
      <button @click="load" class="button-load">Load</button>
    </div>
  </div>
</template>

<style>
.app-container {
  max-width: 100%;
  margin: auto;
  padding: 20px;
  background-color: rgba(
    0,
    0,
    0,
    0.5
  ); /* Warna latar belakang diubah menjadi hitam dengan transparansi */
  color: #fff; /* Warna teks diubah menjadi putih untuk kontras */
  border-radius: 8px;
  backdrop-filter: blur(100px); /* Menambahkan efek blur pada background */
}

.content-container {
  max-width: 600px;
  margin: auto;
  overflow: auto; /* Menambahkan scroll ke dalam kontainer konten */
}

.form-container {
  margin-bottom: 20px;
}

.input-title,
.textarea-content {
  width: 100%;
  padding: 8px;
  margin-bottom: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
  background-color: #333; /* Warna latar input diubah menjadi gelap */
  color: #fff; /* Warna teks input diubah menjadi putih */
}

.button-save,
.button-edit,
.button-delete,
.button-load {
  padding: 10px 20px;
  margin-top: 10px;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  transition: transform 0.3s ease-in-out;
  /* Menambahkan transisi untuk animasi */
}

.button-save:hover,
.button-edit:hover,
.button-delete:hover,
.button-load:hover {
  background-color: #0056b3;
  transform: scale(1.1); /* Menambahkan efek skala saat hover */
}

.articles-list {
  list-style: none;
  padding: 0;
}

.article-item {
  padding: 10px;
  background-color: #222; /* Warna latar item artikel diubah menjadi gelap */
  border-bottom: 1px solid #ccc;
}

.article-title {
  font-size: 18px;
  font-weight: bold;
}

.article-content {
  margin-top: 5px;
  margin-bottom: 10px;
}
</style>

<script>
import { ref, onMounted, reactive } from "vue";
import axios from "axios";

export default {
  setup() {
    const form = reactive({
      id: null,
      title: "    ",
      content: "",
    });
    const articles = ref([]);

    async function load() {
      try {
        const response = await axios.get("http://localhost:3000/articles"); // sambungkan dengan db.json
        articles.value = response.data;
      } catch (error) {
        console.error("Error loading articles:", error);
      }
    }

    async function save() {
      try {
        const url = form.id
          ? `http://localhost:3000/articles/${form.id}`
          : "http://localhost:3000/articles";
        const method = form.id ? "put" : "post";
        const response = await axios[method](url, form);

        articles.value = articles.value.map((article) =>
          article.id === response.data.id ? response.data : article
        );
        form.id = null;
        form.title = "";
        form.content = "";
      } catch (error) {
        console.error("Error saving article:", error);
      }
    }

    function edit(article) {
      form.id = article.id;
      form.title = article.title;
      form.content = article.content;
    }

    async function deleteArticle(article) {
      try {
        await axios.delete(`http://localhost:3000/articles/${article.id}`);
        articles.value = articles.value.filter((a) => a.id !== article.id);
      } catch (error) {
        console.error("Error deleting article:", error);
      }
    }

    onMounted(load);
    return { form, articles, save, edit, deleteArticle };
  },
};
</script>
