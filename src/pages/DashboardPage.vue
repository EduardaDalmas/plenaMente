<template>
  <div class="container">
    <div class="text-center">
      <h4>Estatísticas sobre a saúde mental estudantil</h4>
      <a class="subtitulo-metrica"
        >Análise realizada em um database americano 'Mental Health Students' com
        <b>101</b> estudantes de ambos os sexos, sendo eles:
      </a>
    </div>

    <div class="card-metrica">
      <div class="text-center q-mb-xl">
        <a class="subtitulo-metrica"
          >Análise realizada em um database americano 'Mental Health Students'
          com <b>101</b> estudantes de ambos os sexos, sendo eles:
        </a>
      </div>

      <div class="centralize q-mt-lg">
        <div class="row">
          <div class="text-center col">
            <div class="row">
              <a class="titulo-metrica"><b>Mulheres</b></a>
            </div>
            <div class="row">
              <q-knob
                disable
                show-value
                font-size="12px"
                v-model="mulheres"
                size="100px"
                color="teal"
                track-color="grey-3"
                class="q-ma-md"
              >
                {{ mulheres }}%
              </q-knob>
            </div>
          </div>
          <div class="text-center col">
            <div class="row">
              <a class="titulo-metrica"><b>Homens</b></a>
            </div>
            <div class="row">
              <q-knob
                disable
                show-value
                font-size="12px"
                v-model="homens"
                size="100px"
                color="teal"
                track-color="grey-3"
                class="q-ma-md"
              >
                {{ homens }}%
              </q-knob>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="card-metrica">
      <div class="text-center q-mb-xl">
        <a class="subtitulo-metrica">Estudantes no geral que possuem: </a>
      </div>

      <div class="centralize q-mt-md">
        <div class="row">
          <div class="text-center col">
            <div class="row">
              <a class="titulo-metrica"><b>Depressão</b></a>
            </div>
            <div class="row">
              <q-knob
                disable
                show-value
                font-size="12px"
                v-model="depressao"
                size="100px"
                color="teal"
                track-color="grey-3"
                class="q-ma-md"
              >
                {{ depressao }}%
              </q-knob>
            </div>
          </div>
          <div class="text-center col">
            <div class="row">
              <a class="titulo-metrica"><b>Ansiedade</b></a>
            </div>
            <div class="row">
              <q-knob
                disable
                show-value
                font-size="12px"
                v-model="ansiedade"
                size="100px"
                color="teal"
                track-color="grey-3"
                class="q-ma-md"
              >
                {{ ansiedade }}%
              </q-knob>
            </div>
          </div>
          <div class="text-center col">
            <div class="row">
              <a class="titulo-metrica"><b>Ataque de Pânico</b></a>
            </div>
            <div class="row">
              <q-knob
                disable
                show-value
                font-size="12px"
                v-model="panico"
                size="100px"
                color="teal"
                track-color="grey-3"
                class="q-ma-md"
              >
                {{ panico }}%
              </q-knob>
            </div>
          </div>
          <div class="text-center col">
            <div class="row">
              <a class="titulo-metrica"><b>Ambos transtornos</b></a>
            </div>
            <div class="row">
              <q-knob
                disable
                show-value
                font-size="12px"
                v-model="todos_transtornos"
                size="100px"
                color="teal"
                track-color="grey-3"
                class="q-ma-md"
              >
                {{ todos_transtornos }}%
              </q-knob>
            </div>
          </div>
          <div class="text-center col">
            <div class="row">
              <a class="titulo-metrica"><b>Fazem tratamento</b></a>
            </div>
            <div class="row">
              <q-knob
                disable
                show-value
                font-size="12px"
                v-model="tratamento"
                size="100px"
                color="teal"
                track-color="grey-3"
                class="q-ma-md"
              >
                {{ tratamento }}%
              </q-knob>
            </div>
          </div>
          <div class="text-center col">
            <div class="row">
              <a class="titulo-metrica"><b>Sem transtornos</b></a>
            </div>
            <div class="row">
              <q-knob
                disable
                show-value
                font-size="12px"
                v-model="sem_transtorno"
                size="100px"
                color="teal"
                track-color="grey-3"
                class="q-ma-md"
              >
                {{ sem_transtorno }}%
              </q-knob>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="card-metrica">
      <div class="text-center q-mb-xl">
        <a class="subtitulo-metrica">Mulheres que possuem: </a>
      </div>

      <div class="centralize q-mt-md">
        <div class="row">
          <div class="text-center col">
            <div class="row">
              <a class="titulo-metrica"><b>Depressão</b></a>
            </div>
            <div class="row">
              <q-knob
                disable
                show-value
                font-size="12px"
                v-model="mulheres_depressao"
                size="100px"
                color="teal"
                track-color="grey-3"
                class="q-ma-md"
              >
                {{ mulheres_depressao }}%
              </q-knob>
            </div>
          </div>
          <div class="text-center col">
            <div class="row">
              <a class="titulo-metrica"><b>Ansiedade</b></a>
            </div>
            <div class="row">
              <q-knob
                disable
                show-value
                font-size="12px"
                v-model="mulheres_ansiedade"
                size="100px"
                color="teal"
                track-color="grey-3"
                class="q-ma-md"
              >
                {{ mulheres_ansiedade }}%
              </q-knob>
            </div>
          </div>
          <div class="text-center col">
            <div class="row">
              <a class="titulo-metrica"><b>Ataque de Pânico</b></a>
            </div>
            <div class="row">
              <q-knob
                disable
                show-value
                font-size="12px"
                v-model="mulheres_panico"
                size="100px"
                color="teal"
                track-color="grey-3"
                class="q-ma-md"
              >
                {{ mulheres_panico }}%
              </q-knob>
            </div>
          </div>
          <div class="text-center col">
            <div class="row">
              <a class="titulo-metrica"><b>Ambos transtornos</b></a>
            </div>
            <div class="row">
              <q-knob
                disable
                show-value
                font-size="12px"
                v-model="mulheres_todos_transtornos"
                size="100px"
                color="teal"
                track-color="grey-3"
                class="q-ma-md"
              >
                {{ mulheres_todos_transtornos }}%
              </q-knob>
            </div>
          </div>
          <div class="text-center col">
            <div class="row">
              <a class="titulo-metrica"><b>Fazem tratamento</b></a>
            </div>
            <div class="row">
              <q-knob
                disable
                show-value
                font-size="12px"
                v-model="mulheres_tratamento"
                size="100px"
                color="teal"
                track-color="grey-3"
                class="q-ma-md"
              >
                {{ mulheres_tratamento }}%
              </q-knob>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="card-metrica">
      <div class="text-center q-mb-xl">
        <a class="subtitulo-metrica">Homens que possuem: </a>
      </div>

      <div class="centralize q-mt-md">
        <div class="row">
          <div class="text-center col">
            <div class="row">
              <a class="titulo-metrica"><b>Depressão</b></a>
            </div>
            <div class="row">
              <q-knob
                disable
                show-value
                font-size="12px"
                v-model="homens_depressao"
                size="100px"
                color="teal"
                track-color="grey-3"
                class="q-ma-md"
              >
                {{ homens_depressao }}%
              </q-knob>
            </div>
          </div>
          <div class="text-center col">
            <div class="row">
              <a class="titulo-metrica"><b>Ansiedade</b></a>
            </div>
            <div class="row">
              <q-knob
                disable
                show-value
                font-size="12px"
                v-model="homens_ansiedade"
                size="100px"
                color="teal"
                track-color="grey-3"
                class="q-ma-md"
              >
                {{ homens_ansiedade }}%
              </q-knob>
            </div>
          </div>
          <div class="text-center col">
            <div class="row">
              <a class="titulo-metrica"><b>Ataque de Pânico</b></a>
            </div>
            <div class="row">
              <q-knob
                disable
                show-value
                font-size="12px"
                v-model="homens_panico"
                size="100px"
                color="teal"
                track-color="grey-3"
                class="q-ma-md"
              >
                {{ homens_panico }}%
              </q-knob>
            </div>
          </div>
          <div class="text-center col">
            <div class="row">
              <a class="titulo-metrica"><b>Ambos transtornos</b></a>
            </div>
            <div class="row">
              <q-knob
                disable
                show-value
                font-size="12px"
                v-model="homens_todos_transtornos"
                size="100px"
                color="teal"
                track-color="grey-3"
                class="q-ma-md"
              >
                {{ homens_todos_transtornos }}%
              </q-knob>
            </div>
          </div>
          <div class="text-center col">
            <div class="row">
              <a class="titulo-metrica"><b>Fazem tratamento</b></a>
            </div>
            <div class="row">
              <q-knob
                disable
                show-value
                font-size="12px"
                v-model="homens_tratamento"
                size="100px"
                color="teal"
                track-color="grey-3"
                class="q-ma-md"
              >
                {{ homens_tratamento }}%
              </q-knob>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="card-metrica">
      <div class="text-center q-mb-xl">
        <a class="subtitulo-metrica">Dados sobre o estado civil: </a>
      </div>

      <div class="centralize q-mt-md">
        <div class="row">
          <div class="text-center col">
            <div class="row">
              <a class="titulo-metrica"><b>Mulheres casadas</b></a>
            </div>
            <div class="row">
              <q-knob
                disable
                show-value
                font-size="12px"
                v-model="mulheres_casadas"
                size="100px"
                color="teal"
                track-color="grey-3"
                class="q-ma-md"
              >
                {{ mulheres_casadas }}%
              </q-knob>
            </div>
          </div>
          <div class="text-center col">
            <div class="row">
              <a class="titulo-metrica"><b>Casadas depressão</b></a>
            </div>
            <div class="row">
              <q-knob
                disable
                show-value
                font-size="12px"
                v-model="mulheres_casadas_depressao"
                size="100px"
                color="teal"
                track-color="grey-3"
                class="q-ma-md"
              >
                {{ mulheres_casadas_depressao }}%
              </q-knob>
            </div>
          </div>
          <div class="text-center col">
            <div class="row">
              <a class="titulo-metrica"><b>Homens casados</b></a>
            </div>
            <div class="row">
              <q-knob
                disable
                show-value
                font-size="12px"
                v-model="homens_casados"
                size="100px"
                color="teal"
                track-color="grey-3"
                class="q-ma-md"
              >
                {{ homens_casados }}%
              </q-knob>
            </div>
          </div>
          <div class="text-center col">
            <div class="row">
              <a class="titulo-metrica"><b>Casados depressão</b></a>
            </div>
            <div class="row">
              <q-knob
                disable
                show-value
                font-size="12px"
                v-model="homens_casados_depressao"
                size="100px"
                color="teal"
                track-color="grey-3"
                class="q-ma-md"
              >
                {{ homens_casados_depressao }}%
              </q-knob>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    return {
      mulheres: ref(74.25),
      homens: ref(25.74),
      depressao: ref(34.65),
      ansiedade: ref(32.67),
      panico: ref(33.66),
      tratamento: ref(5.94),
      todos_transtornos: ref(9.9),
      sem_transtorno: ref(36.63),
      mulheres_depressao: ref(38.66),
      mulheres_ansiedade: ref(32),
      mulheres_panico: ref(33.33),
      mulheres_tratamento: ref(6.66),
      mulheres_todos_transtornos: ref(12),
      mulheres_sem_transtorno: ref(36),
      homens_depressao: ref(23.07),
      homens_ansiedade: ref(38.46),
      homens_panico: ref(30.76),
      homens_tratamento: ref(3.84),
      homens_todos_transtornos: ref(3.84),
      homens_sem_transtorno: ref(38.46),
      mulheres_casadas: ref(17.33),
      mulheres_casadas_depressao: ref(100),
      homens_casados: ref(11.53),
      homens_casados_depressao: ref(100),
    };
  },
};
</script>
