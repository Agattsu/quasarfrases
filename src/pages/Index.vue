<template>
  <q-page class="container flex column flex-center justify-around">
    <q-img
      src="https://viverdeblog.com/wp-content/uploads/2014/05/quotes-thumb.png"
      spinner-color="white"
      style="height: auto; max-width: 250px"
    />
    <h5 class="title q-ma-sm text-center">{{ phrases[index] }}</h5>
    <q-btn
      label="Gerar Frase"
      class="button"
      @click="randomPosition"
      stack
      glossy
      color="green-5"
    />
  </q-page>
</template>

<script>
export default {
  name: "PhraseOfDay",
  data() {
    return {
      phrases: [
        "Nem todos os dias são bons, mas há algo bom em cada dia.",
        "Respeite sua mente e trate seu corpo com carinho.",
        "Suba o primeiro degrau com fé. Não é necessário que você veja toda a escada, apenas dê o primeiro pass",
        "Toda manhã você tem duas escolhas: continuar dormindo com seus sonhos ou acordar e persegui-los!",
        "O otimismo é a fé em ação. Nada se pode levar a efeito sem otimismo.",
      ],
      index: 0,
    };
  },
  methods: {
    randomPosition() {
      let index = parseInt(Math.random() * 5 + 0);

      this.index = index;
    },
  },
  beforeMount() {
    this.randomPosition();
  },
};
</script>

<style lang="stylus" scoped>

.container{
  background-color: #e067b8;
}

.title{
  color:#fff;
}

.button{
  width: 90%;
}
</style>
