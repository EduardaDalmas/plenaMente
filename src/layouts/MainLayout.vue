<template>
  <q-layout view="lHh Lpr lFf">
    <q-header class="header">
      <q-toolbar>
        <q-toolbar-title>
          <img class="logo" src="../assets/logo.png" />
        </q-toolbar-title>
        <q-btn
          flat
          @click="drawerRight = !drawerRight"
          round
          dense
          icon="menu"
        />
      </q-toolbar>
    </q-header>

    <q-drawer side="right" v-model="drawerRight" @click="mostraMenu()" bordered>
      <q-scroll-area class="fit">
        <div class="q-pa-md">
          <h5 @click="acessarPage('dashboard')">Análises</h5>
          <h5 @click="acessarPage('home')">Como está se sentindo</h5>
        </div>
      </q-scroll-area>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "MainLayout",

  components: {},

  methods: {
    mostraMenu() {
      if (this.drawerRight == true) {
        this.drawerRight = false;
      } else {
        this.drawerRight = true;
      }
    },

    acessarPage(param) {
      if (param == "home") {
        this.$router.push({ name: "home" });
      }
      if (param == "dashboard") {
        this.$router.push({ name: "dashboard" });
      }
    },
  },

  setup() {
    let drawerRight = ref("false");

    return {
      drawerRight,
    };
  },
});
</script>
