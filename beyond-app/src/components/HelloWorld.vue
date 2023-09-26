<template>
  <div class="hello">
    <h1 :class="`message-${idioma}`">{{ mensagem }}</h1>
    <button @click="alterarIdioma" class="styled-button">Trocar Idioma</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      idioma: 'en',
      mensagens: {
        en: 'Hello World',
        es: 'Hola Mundo',
        pt: 'Olá Mundo '
      }
    };
  },
  computed: {
    mensagem() {
      return this.mensagens[this.idioma];
    }
  },
  methods: {
    alterarIdioma() {
      if (this.idioma === 'en') {
        this.idioma = 'es';
      } else if (this.idioma === 'es') {
        this.idioma = 'pt';
      } else {
        this.idioma = 'en';
      }
    }
  }
};
</script>

<style scoped>
h1 {
  font-family: 'Times New Roman', Times, serif;
  font-size: 30px;
  transition: color 0.3s;
}

.message-en {
  color: blue;
}

.message-es {
  color: red;
}

.message-pt {
  color: green;
}

.styled-button {
  background-color: #4caf50;
  color: white;
  border: none;
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
  border-radius: 5px;
  transition: background-color 0.5s;
}

.styled-button:hover {
  background-color: #45a049;
}

.flag {
  width: 30px;
  height: 20px;
  margin-right: 10px;
  filter: sca(100%); /* Aplica o filtro de escala de cinza */
}


</style>
