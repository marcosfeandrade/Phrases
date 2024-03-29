<template>
  <q-page class="container flex column items-center justify-around">
    <q-img class="img-icon" src="https://cdn.icon-icons.com/icons2/1515/PNG/512/quote_105126.png" spinner-color="white"
      style="height: auto; max-width: 150px" />
    <div clas="phrase-container">
      <h5 class="phrase text-center">{{ phrases[index] }}</h5>
      <span class="author text-accent">— {{ authors[index] ? authors[index] : "desconhecido" }}</span>
    </div>
    <q-btn class="button" color="secondary" icon="autorenew" @click="randomPhrase" label="Randomize" />
  </q-page>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      phrases: [
        'Na vida, não existe nada a temer, mas a entender.',
        'O que sabemos é uma gota; o que ignoramos é um oceano.',
        'Viver é enfrentar um problema atrás do outro. O modo como você o encara é que faz a diferença.',
        'Há verdadeiramente duas coisas diferentes: saber e crer que se sabe. A ciência consiste em saber; em crer que se sabe reside a ignorância.',
        'Faça as coisas o mais simples que você puder, porém não se restrinja às mais simples.',
        'Pouco conhecimento faz com que as pessoas se sintam orgulhosas. Muito conhecimento, com que se sintam humildes.',
        'Um trabalho te dá um propósito e um significado. A vida é vazia sem ambos.',
        'Você não pode ensinar nada a ninguém, mas pode ajudar a pessoas a descobrirem por si mesmas.',
        'Aquele que ousa perder uma hora de seu tempo não sabe o valor da vida.',
        'Em algum lugar, alguma coisa incrível está esperando para ser descoberta.',
        'Ninguém que é curioso é idiota. As pessoas que não fazem perguntas permanecem ignorantes para o resto de suas vidas.',
        'Quem não quer ser aconselhado, não pode ser ajudado.',
        'Construímos muros demais e pontes de menos.'
      ],
      authors: [
        'Marie Curie',
        'Isaac Newton',
        'Benjamin Franklin',
        'Hipócrates',
        'Albert Einstein',
        'Leonardo da Vinci',
        'Stephen Hawking',
        'Galileu Galilei',
        'Charles Darwin',
        'Carl Sagan',
        'Neil DeGrasse Tyson',
        'Neil DeGrasse Tyson',
        'Isaac Newton'
      ],
      index: null,
    };
  },

  methods: {
    randomPhrase() {
      let index = Math.floor(Math.random() * this.phrases.length);
      this.index = index;
    },
  },

  beforeMount() {
    this.randomPhrase();
  }
};
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-start;
  background-color: #fff;
}

.phrase-container {
  left: 50%;
  transform: translate(-50%, -50%);
  color: #000;
}

.phrase {
  font-size: 1.5rem;
  font-weight: 500;
  text-align: center;
}

.author {
  margin-left: 55%;
  font-weight: 450;
  color: #474747
}

.button {
  position: fixed;
  bottom: 10%;
  width: 70%;
  height: 5%;
}
</style>
