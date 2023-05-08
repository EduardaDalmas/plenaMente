<template>
  <q-page class="container">
    <div class="text-center">
      <h4>Como você está se sentindo hoje?</h4>
    </div>
    <div class="centralize">
      <div v-for="item in sentimentos" :key="item" class="col-md-4  virtual-scroll-horizontal">
        <Card :icone="item.icone" :texto="item.texto" :cor="item.cor" @onClickInfo="validaSentimento()"></Card>
      </div>
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'
import Card from '../components/Card.vue'

export default defineComponent({
  name: 'IndexPage',

  components: {
    Card
  },

  setup() {

    let sentimentos = [
      {
        icone: 'sentiment_satisfied',
        texto: 'Feliz',
        cor: '#6BC24C'
      },
      {
        icone: 'sentiment_neutral',
        texto: 'Indiferente',
        cor: '#F5A429'
      },
      {
        icone: 'sentiment_dissatisfied',
        texto: 'Triste',
        cor: '#69CEC8'
      }
    ]

    const validaSentimento = () => {

    }

    return {
      sentimentos,
      validaSentimento
    }
  }


})
</script>
