<template id="my-template" ref="tempTemp">
  <div>
    <v-app-bar
      flat
      :dense="$vuetify.breakpoint.xl"
      :fixed="false"
      scroll-target="#text-title"
      class="top-bar"
      color="white"
    >
      <v-toolbar-title>{{ isFixed() }}</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn small text>{{ !$vuetify.breakpoint.sm }}</v-btn>
      <v-btn small text>Tentang</v-btn>
      <v-btn small text>Layanan Kami</v-btn>
      <v-btn small depressed color="#6897FF" class="white--text"
        >Buat Pesanan</v-btn
      >
    </v-app-bar>
    <v-container fluid class="px-15 ma-0 container">
      <v-row class="full-height first-page">
        <v-col v-if="$vuetify.breakpoint.smAndDown" md="6" cols="12">
          <v-img
            class="mx-auto"
            max-width="50vw"
            max-height="50vw"
            src="/img/header-logo.svg"
          ></v-img>
        </v-col>
        <v-row class="first-page text-container">
          <v-col md="3" cols="3">
            <v-img
              class="ml-auto"
              src="/img/tefa-icon.svg"
              max-height="100px"
              max-width="100px"
            />
          </v-col>
          <v-col md="3" cols="9">
            <h1 class="text-title" id="text-title">Teaching Factory</h1>
            <h4 class="text-sub-title">part of SMK Krian 1</h4>
          </v-col>
          <v-col v-if="$vuetify.breakpoint.mdAndUp" md="6" cols="6">
            <v-img
              max-width="30vw"
              max-height="30vw"
              src="/img/header-logo.svg"
            ></v-img>
          </v-col>
        </v-row>
      </v-row>

      <v-row class="full-height">
        <v-col cols="6">
          <v-img
            class="ml-auto"
            max-width="30vw"
            max-height="30vw"
            src="/img/about-us-logo.svg"
          ></v-img>
        </v-col>
        <v-col>
          <h1 class="about-title">Tentang</h1>
          <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
            eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim
            ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut
            aliquip ex ea commodo consequat. Duis aute irure dolor in
            reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
            pariatur. Excepteur sint occaecat cupidatat non proident, sunt in
            culpa qui officia deserunt mollit anim id est laborum.
          </p>
        </v-col>
      </v-row>

      <v-row class="twice-height">
        <v-col>
          <v-row>
            <v-col>
              <h1 class="about-title text-center">Layanan Kami</h1>
            </v-col>
          </v-row>
          <v-row>
            <v-col>
              <v-img
                width="30vw"
                height="30vw"
                class="mx-auto"
                src="/img/our-service-logo.svg"
              />
            </v-col>
          </v-row>
          <v-row class="mx-5">
            <v-col cols="4" v-for="i in services.length" :key="i">
              <v-hover>
                <template v-slot:default="{ hover }">
                  <!-- F2F6FF white -->
                  <!-- 6897FF blue -->
                  <v-card
                    v-ripple
                    width="25vw"
                    height="25vh"
                    :elevation="hover ? 5 : 0"
                    :class="
                      `mx-auto my-5 inner-service-text ${
                        i % 2 == 0 ? '' : 'white--text'
                      }`
                    "
                    :color="i % 2 == 0 ? '#F2F6FF' : '#6897FF'"
                  >
                    <h1>{{ services[i - 1].name }}</h1>
                  </v-card>
                </template>
              </v-hover>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
    <!-- #264A99 blue -->
    <!-- #1B3368 darker blue -->
    <v-footer padless min-height="30vh" color="#264A99">
      <v-row class="footer">
        <v-col cols="4">
          <v-img
            src="/img/tefa-logo-light.svg"
            class="mx-auto"
            height="7vw"
            width="7vw"
          />
        </v-col>
        <v-col cols="4">
          <v-img
            src="/img/smk-bisa-logo.svg"
            class="mx-auto"
            width="7vw"
            height="7vw"
          />
        </v-col>
        <v-col cols="4">
          <v-img
            src="/img/smk-logo.svg"
            class="mx-auto"
            height="7vw"
            width="7vw"
          />
        </v-col>
        <v-col class="footer-foot" cols="12">
          <h3>© 2021 - Teaching Factory SMK Krian 1 Sidoarjo</h3>
        </v-col>
      </v-row>
    </v-footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isFlat: true,
      scrollPost: null,
      services: [
        {
          name: "Printing"
        },
        {
          name: "Photography"
        },
        {
          name: "Photo/Video Editing"
        },
        {
          name: "Lorem"
        },
        {
          name: "Printing"
        },
        {
          name: "Printing"
        }
      ],
      isFixed: function() {
        return true;
      }
    };
  },
  methods: {
    updateScroll() {
      this.scrollPost = window.scrollY;
    }
  },
  mounted() {
    window.addEventListener("scroll", this.updateScroll);
  },
  destroy() {
    window.removeEventListener("scroll", this.updateScroll);
  }
};
</script>

<style lang="sass">
.container
  font-size: 12px
  color: #424143

*
  // border: 1px solid red

.top-bar
  position: fixed
  z-index: 2

.full-height
  height: 100vh

.twice-height
  height: 175vh

.first-page
  display: flex
  justify-content: center
  align-items: center
  @media only screen and (max-width: 960px)
    align-items: flex-end

.text-container
  @media only screen and (max-width: 960px)
    align-self: flex-start

.text-title
  font-size: 1.7rem

.text-sub-title
  font-weight: 400
  font-size: 1rem

.text-title, .text-sub-title
  display: flex
  justify-content: flex-start

.about-title
  font-size: 1.5rem

.inner-service-text
  display: flex
  justify-content: center
  align-items: center
  cursor: pointer

.footer
  height: 30vh

.footer-foot
  background: #1B3368
  align-self: flex-end
  text-align: center

.footer-foot h3
  color: white
  font-weight: 300
</style>
