<template>
  <div class="bg-gray-800 py-3 flex flex-col space-y-5">
    <div
      v-if="curoute.includes('/dashboard')"
      class="w-full clickable text-c sm:px-20 px-10 m-0-auto border-b pb-3"
      @click="scrolltop"
    >
      <a
        class="clickable w-fit text-white block font-semibold size-12 m-0-auto"
        @click="scrolltop"
        >Aller en haut de la page</a
      >
    </div>
    <div
      class="flex w-fit m-0-auto sm:px-10 px-10 pt-5 border-b pb-5"
      :class="{
        'space-x-10 align-center': size > 1200,
        'flex-col': size <= 1200,
      }"
    >
      <div :class="{ 'py-3': size <= 1200 }">
        <div class="mt-2">
          <nuxt-link
            to="/ofalooagent/guide"
            class="underline-hover text-c w-fit text-white block size-13"
            :class="{ 'w-autoxx': size <= 1200 }"
            >Guide d'utilisations</nuxt-link
          >
        </div>
      </div>
      <div :class="{ 'py-3': size <= 1200 }">
        <div class="mt-2">
          <nuxt-link
            to="/ofalooagent/condition-utilisation"
            class="underline-hover text-c w-fit text-white block size-13"
            :class="{ 'w-autoxx': size <= 1200 }"
            >Conditions d'utilisations</nuxt-link
          >
        </div>
      </div>
      <div :class="{ 'py-3': size <= 1200 }">
        <div class="mt-2">
          <nuxt-link
            to="/ofalooagent/politique"
            class="underline-hover text-c w-fit text-white block size-13"
            :class="{ 'w-autoxx': size <= 1200 }"
            >Politique de confidentialité</nuxt-link
          >
        </div>
      </div>
      <div :class="{ 'py-3': size <= 1200 }">
        <div class="mt-2">
          <nuxt-link
            to="/ofalooagent/contactez-nous"
            class="underline-hover text-c w-fit text-white block size-13"
            :class="{ 'w-autoxx': size <= 1200 }"
            >Nous contacter</nuxt-link
          >
        </div>
      </div>
      <div
        class="flex flex-col justify-center"
        :class="{ 'py-3': size <= 1200 }"
      >
        <h4
          class="w-fit text-white text-c block font-semibold size-16"
          :class="{ 'w-autoxx': size <= 1200 }"
        >
          <home
            :color="'#fff'"
            :scale="10"
            :textcolor="'#fff'"
            :textscale="50"
          ></home>
        </h4>
        <div class="mt-2 flex flex-col space-y-1">
          <a
            class="w-fit text-white text-c block size-13"
            :class="{ 'w-autoxx': size <= 1200 }"
            >Rejoignez-nous sur les réseaux</a
          >
          <p
            class="flex align-center justify-center space-x-4 text-white pt-1"
            :class="{ 'w-autoxx': size <= 1200 }"
          >
            <a href="#" target="_blank"
              ><i class="fab fa-twitter size-20 clickable color-white"></i
            ></a>
            <a href="#" target="_blank"
              ><i class="fab fa-facebook size-20 clickable color-white"></i
            ></a>
            <a href="#" target="_blank"
              ><i class="fab fa-instagram size-20 clickable color-white"></i
            ></a>
            <a href="#" target="_blank"
              ><i class="fab fa-tiktok size-20 clickable color-white"></i
            ></a>
            <a href="#" target="_blank"
              ><i class="fab fa-youtube size-20 clickable color-white"></i
            ></a>
            <!-- <a href="https://fb.com/saliistore" target="_blank"
              ><i class="fab fa-linkedin-in size-20 clickable color-white"></i
            ></a> -->
          </p>
        </div>
      </div>
    </div>
    <div
      class="w-fit flex align-center m-0-auto pt-6 pb-2"
      :class="{ 'space-x-5': size > 540, 'flex-col space-y-5': size <= 540 }"
    >
      <div class="w-fit mx-2 flex align-center space-x-1 size-14 text-white">
        <span class="text-white">{{ toyear }}, Xunita</span>
        <span class="text-white">•</span>
        <a
          v-if="!curoute.includes('/dashboard')"
          href="/"
          class="w-fit text-white block size-13"
          >Ofaloo Agentcenter</a
        >
        <a v-else href="/dashboard" class="w-fit text-white block size-13"
          >Ofaloo Agentdashboard</a
        >
      </div>
    </div>
  </div>
</template>

<script>
import Home from '../logo/Home.vue'
export default {
  components: { Home },
  computed: {
    toyear() {
      return new Date().getFullYear().toString()
    },
    size() {
      return this.$store.state.size
    },
    curoute() {
      return this.$route.path
    },
  },
  methods: {
    scrolltop() {
      window.scroll({
        top: 0,
        left: 0,
        behavior: 'smooth',
      })
    },
  },
}
</script>

<style scoped></style>
