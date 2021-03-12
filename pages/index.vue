<template>
  <v-container fluid class="pa-0 ma-0">
    <v-app-bar flat dense fixed class="top-bar" color="white">
       <v-toolbar-title></v-toolbar-title>
       <v-spacer></v-spacer>
       <v-btn small text>Beranda</v-btn>
       <v-btn small text>Tentang</v-btn>
       <v-btn small text>Layanan Kami</v-btn>
       <v-btn small depressed color="#6897FF" class="white--text">Buat Pesanan</v-btn>
    </v-app-bar>

    <v-row class="full-height first-page">
      <v-col>
        <h1 class="text-title">Teaching Factory</h1>
        <h4 class="text-sub-title">part of SMK Krian 1</h4>
      </v-col>
      <v-col>
        <v-img max-width="500px" max-height="500px" src="/img/header-logo.svg"></v-img>
      </v-col>
    </v-row>
    
    <v-row class="full-height second-page">
      <v-col>
        <v-img max-width="500px" max-height="500px" src="/img/about-us-logo.svg"></v-img>
      </v-col>
      <v-col>
        <h1>About Us</h1>
      </v-col>
    </v-row>

  </v-container>
</template>

<script>
export default {};
</script>

<style lang="sass">
*
  // border: 1px solid red

.full-height
  height: 100vh

.first-page
  display: flex
  justify-content: center
  align-items: center

.text-title, .text-sub-title
  padding: 0 0 0 15rem

.text-title:before
  content: ""
  background: url("/img/tefa-icon.svg")
  width: 5rem
  height: 5rem
  left: 10rem
  position: absolute

.text-sub-title
  font-weight: 400
</style>
