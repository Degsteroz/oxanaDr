<template>
  <div class="invite__container">
    <div class="invite__imageWrapper">
      <h1>{{greeting}}</h1>
      <div>
        <img
            v-for="(image, index) in guest.images"
            :src="image"
            :key="image"
            class="invite__image"
            :style="{marginLeft: -100 * index + 'px'}"
        />
      </div>
    </div>
    <div class="invite__textWrapper">
        <h2>{{greetings}}</h2>
        <div class="text__address">
          Место проведение <a :href="url" target="_blank">{{place}}</a>
        </div>
        <div>
          {{dressCode}}
        </div>
        <img :src="dressCodeImage" class="text__noSportImage"/>
      </div>
  </div>
</template>
<script setup>
import pageData from '../data/data'
const urlParams = new URLSearchParams(window.location.search);
const guestId = urlParams.get('guest')

const {
    guests,
    greetings,
    place,
    url,
    dressCode,
    dressCodeImage,
} = pageData
const guest = guests[guestId]
const {names: guestNames} = guest

const greeting = guestNames.length > 1
    ? `Дорогие ${guestNames[0]} и ${guestNames[1]}`
    : `Дорогая ${guestNames[0]}`

</script>

<style scoped>
.invite__container {
  display: flex;
  width: 100%;
  background-color: #b700ff;
  padding: 30px;
  justify-content: space-between;
}
.invite__imageWrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.invite__textWrapper {
  max-width: 50%;
  text-align: center;
}
.invite__image {
  width: 300px;
  border-radius: 50%;
}
h2 {
  margin-bottom: 30px;
}
.text__address {
  font-size: 25px;
}
.text__noSportImage {
  width: 250px;
}

@media (min-width: 460px) {
  .invite__container {
    flex-direction: column;
    text-align: center;
    padding: 30px 5px;
  }
  .invite__textWrapper {
    max-width: 100%;
    align-items: center;
  }
  .invite__image {
    width: 60%;
  }
}
</style>
