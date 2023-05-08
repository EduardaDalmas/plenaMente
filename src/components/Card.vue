<template>
  <q-card class="card flat bordered">
    <q-card-section>
      <div class="row">
      <q-icon class="icone " :name="icone"  v-bind:style="{ 'color': cor }"></q-icon>
    </div>
    </q-card-section>
    <div class="row">
      <q-chip class="chip" v-bind:style="{ 'background-color': cor }">{{ texto }}</q-chip>
    </div>
  </q-card>

</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'CardComponent',
  props: {
    texto: {
      type: String,
      required: true
    },

    icone: {
      type: String,
      default: '#'
    },

    cor: {
      type: String,
      default: '#'
    },
  }
})
</script>
