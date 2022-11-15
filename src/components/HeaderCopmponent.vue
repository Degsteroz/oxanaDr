<template>
  <div class="header">
    <img
        :src="cakeSrc"
        class="header__image"
    />
    <img
        src="../assets/headerImage.png"
        class="header__imageText"
    />
    <img
        :src="cakeSrc"
        class="header__image"
    />
  </div>
</template>
<script setup>
const cakeSrc = 'https://www.wordsjustforyou.com/wp-content/uploads/2021/08/Happy-Birthday-Cake-Candles-Gif_02_wordsjustforyou_200821.gif'
</script>

<style scoped>
.header {
  display: flex;
  gap: 40px;
  justify-content: center;
  align-items: center;
  width: 100%;
  background: radial-gradient(circle, rgba(131,58,180,1) 0%, rgba(253,29,29,1) 50%, rgba(252,176,69,1) 100%);
  padding: 40px 0;

  font-size: 30px;
  color: red;
}
.header__image {
  width: 100px;
  height: 100px;
}
.header__imageText {
  width: 700px;
}

@media (max-width: 600px) {
  .header {
    flex-direction: column;
    padding: 5px;
    background: aqua;
  }
  .header__image {
    width: 50px;
    height: 50px;
  }
  .header__imageText {
    width: 100%;
  }
}
</style>
