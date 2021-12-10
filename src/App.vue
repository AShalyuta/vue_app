<template>
  <div id="app">
    <div class="content">
      <h2>Получите все факты, связанные с аниме</h2>
      <b>Поиск факта:</b>
      <form @submit.prevent="submitAnimeNumber">
        <br>
        Название аниме:
        <br>
        <input type="text"
          v-model="nameanime"
          placeholder="attack_on_titan"
        />
        <h1>Список аниме</h1>
        <h3>
        dragon_ball
        <br>
        bleach
        <br>
        black_clover
        <br>
        jujutsu_kaisen
        <br>
        fma_brotherhood
        <br>
        naruto
        <br>
        gintama
        <br>
        one_piece
        <br>
        demon_slayer
        <br>
       attack_on_titan
        <br>
        hunter_x_hunter
        <br>
        boku_no_hero_academia
        </h3>
        <br>
        Номер фактора:
        <br>
        <input type="text"
          v-model="idfact"
          placeholder="1"
        />
        <br>
        <br>
        <button type="submit">Найти</button>
      </form>
    </div>
    <div class="factсontent">
      <h1>{{ outputFact }}</h1>
    </div>
  </div>
</template>

<script>
import Axios from 'axios';
export default {
  name: 'App',
  data() {
    return {
      outputFact: '',
      nameanime: '',
      idfact: '',
    }
  },
  methods: {
    submitAnimeNumber() {
      Axios.get(`https://anime-facts-rest-api.herokuapp.com/api/v1/${this.nameanime}/${this.idfact}`).then((res) => {     
      this.outputFact = res.data.data.fact;   
      });
    }
  },
}
</script>

<style>
html,
body {
  height:100%;
}
#app {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100%;
  background: #F0FFFF;
  position:relative;
}
.content {
  background: #00FFFF;
  text-align: center;
  border-radius: 10px;
  }
.factсontent {
  position:absolute;
  bottom:0;
  background: #1E90FF;
  text-align: center;
  border-radius: 20px;
}
</style>
