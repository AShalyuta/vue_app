<template>
  <div class="header">
      <router-link to="/" class="header-menubutton">
        Главная
      </router-link>
      Разработал Шалюта Александр Николаевич, студент ГГУ им. Ф. Скорины
      <router-link to="/about" class="header-menubutton">
        Библеотека аниме
      </router-link>
  </div>
</template>

<script>
export default {
  
}
</script>

<style lang="scss" scoped>
  .header {
    display: flex;
    justify-content: space-between;
    background: #FFA500;
    width: 100%;
  }
  .header-menubutton {
    background: #FFA500;
    border-radius: 10px;
    margin: 8px;
    padding: 8px;
    border: solid 1px #000;
  }
  .header-logoimg {
    width: 20px;
    height: 20px;
  } 
</style>