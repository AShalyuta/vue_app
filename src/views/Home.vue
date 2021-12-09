<template>
  <div class="content">
    <h2>Получите все факты, связанные с аниме</h2>
    <ol>
      <b>Поиск факта:</b>
      <form @submit.prevent="submitAnimeNumber">
        <br>
        Название аниме:
        <br>
        <input type="text"
          v-model="nameanime"
          placeholder="attack_on_titan"
        />
        <br>
        Номер фактора:
        <br>
        <input type="text"
          v-model="idfact"
          placeholder="1"
        />
        <br>
        <button type="submit">Найти</button>
      </form>
      <h1>{{ outputFact }}</h1>
    </ol>
  </div>
</template>

<script>
import Axios from 'axios';
export default {
  data() {
    return {
      outputFact: '',
      nameanime: '',
      idfact: '',
    }
  },
  methods: {
    submitAnimeNumber() {
      let url = "";
      url = `https://anime-facts-rest-api.herokuapp.com/api/v1/${this.nameanime}/${this.idfact}`;
      Axios.get(url)
      .then((response) => response.data)
      .then((fact) => {
        this.outputFact = fact;
      });
    }
  },
}
</script>

<style lang="scss">
  .content {
    background: #FFD700;
    width: 100%;
    flex: 1 0 auto;
    h2,h3,h4 {
      text-align: center;
    }
    ol {
      background: #DAA520;
    }
    input {
      margin-bottom: 10px;
      margin-right: 3px;
    }
  }
</style>