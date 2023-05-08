<template>
  <q-page class="container">
    <div class="text-center">
      <h4>Como você está se sentindo hoje?</h4>
    </div>

    <div class="centralize bloco-sentimentos">
      <div v-for="item in sentimentos" :key="item" class="col-md-4">
        <Card
          :icone="item.icone"
          :texto="item.texto"
          :cor="item.cor"
          @onClickInfo="validaSentimento(item.texto, item.cor)"
        ></Card>
      </div>
    </div>

    <div
      v-if="mostraConselho"
      class="centralize card-recomendacoes"
      v-bind:style="{ 'background-color': corHumor }"
    >
      <div class="text-center bloco-recomendacoes">
        <h6>Hoje você está se sentindo {{ humor }}...</h6>
        <p>{{ introducao }}</p>
        <div v-for="item in recomendacoes" :key="item">
          <li>{{ item.texto }}</li>
        </div>
        <p>{{ conclusao }}</p>
      </div>
    </div>
  </q-page>
</template>

<script>
import { defineComponent, ref } from "vue";
import Card from "../components/Card.vue";

export default defineComponent({
  name: "IndexPage",

  components: {
    Card,
  },

  setup() {
    let corHumor = ref("");
    let mostraConselho = ref(false);
    let humor = ref("");
    let recomendacoes = ref([]);
    let introducao = ref("");
    let conclusao = ref("");
    let sentimentos = [
      {
        icone: "fa-regular fa-face-smile",
        texto: "Feliz",
        cor: "#6BC24C",
      },
      {
        icone: "fa-regular fa-face-meh",
        texto: "Indiferente",
        cor: "#F5A429",
      },
      {
        icone: "fa-regular fa-face-sad-tear",
        texto: "Triste",
        cor: "#69CEC8",
      },
      {
        icone: "fa-regular fa-face-tired",
        texto: "Nervoso",
        cor: "#f2d43f",
      },
      {
        icone: "fa-regular fa-face-angry",
        texto: "Irritado",
        cor: "#eb1c23",
      },
      {
        icone: "fa-regular fa-face-flushed",
        texto: "Esgotado",
        cor: "#5b07a6",
      },
    ];

    const validaSentimento = (param, cor) => {
      mostraConselho.value = true;
      corHumor.value = cor;
      humor.value = param.toLowerCase();
      if (humor.value == "triste") {
        introducao.value =
          "Se você está se sentindo triste, é importante lembrar que é normal sentir-se assim de vez em quando. No entanto, se a tristeza persistir por um longo período de tempo ou começar a afetar sua capacidade de funcionar no dia a dia, é importante procurar ajuda profissional. Além disso, aqui estão algumas sugestões que podem ajudar a lidar com a tristeza:";
        recomendacoes.value = [
          {
            texto:
              "Pratique a auto-compaixão: em vez de se julgar por se sentir triste, seja gentil consigo mesmo e lembre-se de que todos passam por momentos difíceis.",
          },
          {
            texto:
              "Faça atividades que você gosta: reserve um tempo para fazer coisas que normalmente lhe trazem alegria, como ler, ouvir música ou sair com amigos.",
          },
          {
            texto:
              "Fale com alguém: conversar com amigos, familiares ou um terapeuta pode ajudar a aliviar a tristeza e a solidão.",
          },
          {
            texto:
              "Pratique hábitos saudáveis: cuidar do seu corpo pode ajudar a melhorar o seu humor. Tente fazer exercícios, comer alimentos saudáveis, dormir bem e evitar álcool e drogas.",
          },
        ];
        conclusao.value =
          "Lembre-se de que é normal sentir-se triste às vezes, mas há muitas coisas que você pode fazer para lidar com essa emoção e começar a se sentir melhor. Se você precisar de ajuda adicional, não hesite em procurar um profissional de saúde mental ou um médico.";
      }

      if (humor.value == "indiferente") {
        introducao.value =
          "Se você se sente indiferente, pode ser um sinal de que está passando por um período de desconexão emocional. Isso pode ser resultado de diversos fatores, incluindo estresse, ansiedade, depressão, mudanças na vida ou simplesmente cansaço. Aqui estão algumas sugestões que podem ajudar a lidar com essa sensação de indiferença:";
        recomendacoes.value = [
          {
            texto:
              "Faça uma pausa: tire um tempo para si mesmo e se permita descansar e relaxar. Isso pode ajudar a reduzir o estresse e a ansiedade que podem estar contribuindo para a sua indiferença.",
          },
          {
            texto:
              "Tente se reconectar com suas emoções: faça uma lista de coisas que costumavam trazer emoção e satisfação à sua vida e tente fazer algumas dessas atividades novamente.",
          },
          {
            texto:
              "Explore novas atividades: tente experimentar coisas novas que possam ajudá-lo a se sentir mais animado e envolvido.",
          },
          {
            texto:
              "Converse com alguém: falar com amigos ou familiares pode ajudar a aumentar sua conexão com outras pessoas e melhorar seu humor.",
          },
          {
            texto:
              "Procure ajuda profissional: se a indiferença persistir ou se tornar um problema significativo, pode ser útil procurar ajuda de um terapeuta ou outro profissional de saúde mental.",
          },
        ];
        conclusao.value =
          "Lembre-se de que é normal sentir-se indiferente de vez em quando, mas se você estiver enfrentando esse sentimento com frequência ou se sentir como se estivesse perdendo o controle, pode ser necessário procurar ajuda profissional. Há muitas opções disponíveis, e um profissional de saúde mental pode ajudá-lo a encontrar maneiras de lidar com seus sentimentos e recuperar sua conexão emocional.";
      }

      if (humor.value == "estressado") {
        introducao.value =
          "Se você é um estudante e está se sentindo nervoso, é importante lembrar que muitas pessoas passam por isso e é normal sentir-se assim às vezes. O nervosismo pode ser causado por muitos fatores, como a pressão para ter um bom desempenho acadêmico, preocupações com o futuro ou simplesmente uma carga excessiva de trabalho. Aqui estão algumas sugestões que podem ajudar a lidar com o nervosismo:";
        recomendacoes.value = [
          {
            texto:
              "Faça uma lista: liste as tarefas que você precisa realizar e divida-as em pequenas etapas para que pareçam mais gerenciáveis.",
          },
          {
            texto:
              "Reserve um tempo para relaxar: faça uma pausa e faça algo que você goste para aliviar a tensão. Isso pode incluir atividades como ouvir música, meditar, caminhar ou praticar exercícios físicos.",
          },
          {
            texto:
              "Organize-se: mantenha um cronograma e tente planejar seus estudos e outras atividades de forma organizada. Isso pode ajudá-lo a se sentir mais no controle da situação.",
          },
          {
            texto:
              "Fale com alguém: converse com amigos, familiares ou professores sobre suas preocupações. Eles podem oferecer conselhos úteis e oferecer apoio emocional.",
          },
          {
            texto:
              "Mantenha uma perspectiva positiva: tente manter uma perspectiva positiva e lembre-se de que o nervosismo pode ser superado. Lembre-se também de que o sucesso não é medido apenas pelo desempenho acadêmico, mas também pelo seu desenvolvimento pessoal.",
          },
        ];
        conclusao.value =
          "Lembre-se de que o nervosismo é uma emoção comum e que muitas pessoas passam por isso. Se você precisar de ajuda adicional, considere falar com um profissional de saúde mental ou conselheiro educacional. Eles podem ajudá-lo a lidar com o nervosismo e desenvolver estratégias para lidar com ele de maneira saudável e eficaz.";
      }

      if (humor.value == "irritado") {
        introducao.value =
          "Se você está se sentindo irritado, é importante primeiro tentar identificar a causa desse sentimento. A irritação pode ser causada por diversos fatores, como situações estressantes, frustrações, cansaço ou até mesmo problemas de saúde. Identificar a causa pode ajudá-lo a encontrar maneiras de lidar com ela de forma mais eficaz. Aqui estão algumas sugestões que podem ajudar a lidar com a irritação:";
        recomendacoes.value = [
          {
            texto:
              "Respire fundo: quando se sentir irritado, tente respirar profundamente e lentamente por alguns minutos. Isso pode ajudá-lo a relaxar e a acalmar suas emoções.",
          },
          {
            texto:
              "Faça uma pausa: se possível, tire uma pausa para se afastar da fonte de sua irritação. Isso pode ajudá-lo a se acalmar e a ganhar uma perspectiva mais clara da situação.",
          },
          {
            texto:
              "Exercite-se: o exercício físico pode ajudar a liberar a tensão e o estresse que podem estar causando sua irritação.",
          },
          {
            texto:
              "Encontre atividades relaxantes: encontre atividades que ajudem a relaxar e a acalmar sua mente, como ler um livro, ouvir música, meditar ou fazer um hobby.",
          },
          {
            texto:
              "Comunique-se: tente comunicar seus sentimentos de forma clara e assertiva. Explique como você se sente e por que está irritado. Isso pode ajudar a resolver a situação e evitar que a irritação se transforme em raiva.",
          },
        ];
        conclusao.value =
          "Lembre-se de que é normal sentir irritação às vezes, mas se a irritação estiver interferindo em sua vida diária ou causando problemas em seus relacionamentos, pode ser útil procurar a ajuda de um profissional de saúde mental para trabalhar com você em estratégias eficazes para lidar com essa emoção.";
      }

      if (humor.value == "esgotado") {
        introducao.value =
          "Se você está se sentindo esgotado, pode ser que esteja sobrecarregado com muitas responsabilidades e pressões, ou pode estar enfrentando um período de estresse intenso. Aqui estão algumas sugestões que podem ajudá-lo a lidar com o esgotamento:";
        recomendacoes.value = [
          {
            texto:
              "Tire um tempo para descansar: é importante tirar um tempo para si mesmo e descansar. Faça algo que lhe dê prazer, como ler um livro, assistir a um filme ou passar tempo com amigos e familiares.",
          },
          {
            texto:
              "Durma bem: o sono é fundamental para o bem-estar físico e emocional. Tente estabelecer uma rotina de sono saudável e respeite-a todos os dias.",
          },
          {
            texto:
              "Exercite-se: o exercício físico pode ajudar a reduzir o estresse e a ansiedade, além de melhorar o humor e a qualidade do sono.",
          },
          {
            texto:
              "Pratique a meditação ou a ioga: essas práticas podem ajudar a acalmar a mente e a reduzir o estresse.",
          },
          {
            texto:
              "Identifique e estabeleça limites saudáveis: identifique as áreas de sua vida que estão causando estresse e defina limites saudáveis para proteger seu tempo e energia.",
          },
          {
            texto:
              "Procure ajuda: se você sentir que está sobrecarregado ou se estiver enfrentando problemas emocionais mais profundos, não hesite em procurar ajuda profissional. Um psicólogo ou terapeuta pode ajudá-lo a desenvolver estratégias para lidar com o esgotamento e melhorar sua saúde mental.",
          },
        ];
        conclusao.value =
          "Lembre-se de que o esgotamento é um sinal de que algo precisa mudar em sua vida. Ao tomar medidas para reduzir o estresse e cuidar de si mesmo, você pode melhorar seu bem-estar geral e recuperar sua energia e vitalidade.";
      }

      if (humor.value == "feliz") {
        introducao.value =
          "Se você está se sentindo feliz, isso é maravilhoso! A felicidade é uma emoção positiva que pode trazer muitos benefícios à sua vida, incluindo redução do estresse, melhora do humor e aumento da motivação. Aqui estão algumas sugestões para manter essa sensação de felicidade:";
        recomendacoes.value = [
          {
            texto:
              "Agradeça: pratique a gratidão diariamente, fazendo uma lista das coisas pelas quais você é grato. Isso pode ajudar a aumentar sua sensação de felicidade e satisfação.",
          },
          {
            texto:
              "Compartilhe sua felicidade: compartilhe sua felicidade com amigos e familiares, isso pode trazer alegria para outras pessoas também.",
          },
          {
            texto:
              "Mantenha um estilo de vida saudável: cuidar do seu corpo com uma dieta saudável, exercícios regulares e sono adequado pode ajudar a manter sua felicidade.",
          },
          {
            texto:
              "Faça coisas que você gosta: reserve um tempo para fazer coisas que você realmente gosta, como hobbies, viagens ou passar tempo com amigos.",
          },
          {
            texto:
              "Mantenha a perspectiva: lembre-se de que a felicidade pode ser uma emoção passageira e que é normal passar por altos e baixos emocionais. Mantenha uma perspectiva positiva e aproveite cada momento.",
          },
        ];
        conclusao.value =
          "Lembre-se de que a felicidade é uma emoção positiva, mas também é normal experimentar outros sentimentos. Se você precisar de ajuda para lidar com emoções negativas, não hesite em procurar ajuda de um profissional de saúde mental ou médico.";
      }
    };

    return {
      sentimentos,
      validaSentimento,
      humor,
      mostraConselho,
      introducao,
      recomendacoes,
      conclusao,
      corHumor,
    };
  },
});
</script>
