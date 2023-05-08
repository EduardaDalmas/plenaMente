<template>
  <q-layout view="lHh Lpr lFf">
    <q-header  class="header">
      <q-toolbar >
        <q-btn
          flat
          round
        />

        <q-toolbar-title>
         <img class="logo" src="../assets/logo.png"/>
        </q-toolbar-title>

      </q-toolbar>
    </q-header>


    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from 'vue'


export default defineComponent({
  name: 'MainLayout',

  components: {
  },

  setup () {


  }
})
</script>
