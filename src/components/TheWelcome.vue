<script setup>
import WelcomeItem from "./WelcomeItem.vue";
import DocumentationIcon from "./icons/IconDocumentation.vue";
import ToolingIcon from "./icons/IconTooling.vue";
import EcosystemIcon from "./icons/IconEcosystem.vue";
import CommunityIcon from "./icons/IconCommunity.vue";
import SupportIcon from "./icons/IconSupport.vue";
</script>

<template>
  <WelcomeItem>
    <template #icon>
      <DocumentationIcon />
    </template>
    <template #heading>Pendidikan</template>

    Saat ini saya kuliah di salah satu Kampus swasta di Riau yaitu
    <a href="https://uir.ac.id/" target="_blank" rel="noopener"
      >Universitas Islam Riau</a
    >
    .Sebelumnya saya bersekolah di SMA NEGRI
    <a
      href="https://dapo.kemdikbud.go.id/sekolah/84854CF2F65B3D7824A8"
      target="_blank"
      rel="noopener"
      >SMAN 1 Ukui</a
    >
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <ToolingIcon />
    </template>
    <template #heading>Tempat, Tanggal Lahir</template>

    Saya Lahir di Provinsi
    <a href="https://www.riau.go.id/" target="_blank" rel="noopener"
      >Provinsi Riau</a
    >yaitu
    <a
      href="https://pelalawankab.bps.go.id/publication/2023/09/26/c22022a0fc26d1cfea1daee7/kecamatan-ukui-dalam-angka-2023.html"
      target="_blank"
      rel="noopener"
      >kota Medan</a
    >
    .pada tanggal 6 Februari 2004
    <a
      href="https://github.com/johnsoncodehk/volar"
      target="_blank"
      rel="noopener"
    ></a>
    <a href="https://www.cypress.io/" target="_blank" rel="noopener"></a>

    <a
      href="https://on.cypress.io/component"
      target="_blank"
      rel="noopener"
    ></a>

    <br />
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <EcosystemIcon />
    </template>
    <template #heading>Jurusan</template>

    Prodi atau Jurusan Kuliah Saya mengambil Program didik Teknik Informatika
    atau biasa disebut IT , sekarang saya berada di semester 4 dan berada di
    kelas paling wibu yaitu
    <a
      href="https://www.instagram.com/b1universe_?igsh=bHgzd2gwN2s1OHUw"
      target="_blank"
      rel="noopener"
      >b1universe_</a
    >
    <a href="https://router.vuejs.org/" target="_blank" rel="noopener"></a>
    <a href="https://test-utils.vuejs.org/" target="_blank" rel="noopener"></a>
    <a
      href="https://github.com/vuejs/devtools"
      target="_blank"
      rel="noopener"
    ></a>
    <a
      href="https://github.com/vuejs/awesome-vue"
      target="_blank"
      rel="noopener"
    ></a>
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <CommunityIcon />
    </template>
    <template #heading>Hobi</template>

    Hobi saya Adalah sebagai berikut :
    <br />

    <a href="https://www.goal.com/id" target="_blank" rel="noopener"
      >1. sepak bola</a
    >
    <br />
    <a
      href="https://kumparan.com/pengertian-dan-istilah/pengertian-permainan-bulu-tangkis-dan-sejarahnya-di-indonesia-215E4wCJURX"
      target="_blank"
      rel="noopener"
    ></a
    ><br />
    <a
      href="https://biz.kompas.com/read/2021/02/05/161000028/agar-ngegame-jadi-lebih-seru-gamers-wajib-punya-5-perlengkapan-ini"
      target="_blank"
      rel="noopener"
    >
    </a>
    <br />
    <a href="https://twitter.com/vuejs" target="_blank" rel="noopener"></a>
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <SupportIcon />
    </template>
    <template #heading>Social Media</template>

    Saya kurang aktif di sosial media hanya sekedar gabut saja
    <a
      href="https://www.instagram.com/00zzyy__?igsh=MWFxdGhvc2w5aHQxdA=="
      target="_blank"
      rel="noopener"
    ></a>
  </WelcomeItem>
</template>
