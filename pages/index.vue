<template>
  <div>
    <div class="preview-popular">
      <h1>Популярное</h1>
      <div class="preview-container">
        <div class="preview-images">
          <h2>Вариативные отношения Hytale</h2>
        </div>
        <div class="preview-mini">
          <div class="preview-images-mini">
            <h3>Серверные настройки</h3>
          </div>
          <div class="preview-images-mini">
            <h3>Графика в Hytale</h3>
          </div>
        </div>
        <div class="bar">
        </div>
      </div>
    </div>
    
    <div class="carousel-container">
      <div class="carousel-text-header">
        <h2 class="header-text">Моды</h2>
        <nuxt-link to="/mods">Показать всё...</nuxt-link>
      </div>
      <hooper :items-to-show="3.8" :items-to-slide="1" :wheelControl="false" class="carousel">
        <slide v-for="(slide, key) in carousels[0]" :key="key">
          {{ slide.name }}
        </slide>
        <hooper-navigation slot="hooper-addons" />
      </hooper>
    </div>

    <div class="carousel-container">
      <div class="carousel-text-header">
        <h2 class="header-text">Карты</h2>
        <nuxt-link to="/maps">Показать всё...</nuxt-link>
      </div>
      <hooper :items-to-show="3.8" :items-to-slide="1" :wheelControl="false" class="carousel">
        <slide v-for="(slide, key) in carousels[1]" :key="key">
          {{ slide.name }}
        </slide>
        <hooper-navigation slot="hooper-addons" />
      </hooper>
    </div>
  </div>
</template>

<script>
import { Hooper, Slide, Navigation as HooperNavigation } from 'hooper'
import './../node_modules/hooper/dist/hooper.css'

export default {
  components: {
    Hooper,
    Slide,
    HooperNavigation
  },
  data() {
    return {
      carousels: [
        [
          { name: 'Nsada' },
          { name: 'Nsada' },
          { name: 'Nsada' },
          { name: 'Nsada' }
        ],
        [
          { name: 'Nsada' },
          { name: 'Nsada' },
          { name: 'Nsada' },
          { name: 'Nsada' }
        ]
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.carousel-container {
  margin-top: 5rem;
}

.carousel {
  margin-top: 1rem;
}

.carousel-text-header {
  display: flex;
  font-display: row;
  justify-content: space-between;
  align-items: center;
}

.preview-popular {
  margin-top: 2rem;
}

.preview-container {
  display: flex;
  justify-content: space-between;
  margin-top: 1rem;
}

.preview-images {
  height: 25rem;
  width: 45rem;
  background: url("./../static/hytale/screenshots/2.jpg") no-repeat;
  background-size: 100%;
}

.preview-mini {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.preview-images-mini {
  height: 11rem;
  width: 20rem;
  background: url("./../static/hytale/screenshots/8.jpg") no-repeat;
  background-size: 100%;
}

.preview-images-mini:nth-child(2) {
  height: 11rem;
  width: 20rem;
  background: url("./../static/hytale/screenshots/5.jpg") no-repeat;
  background-size: 100%;
}

.bar {
  height: 25rem;
  width: 18rem;
  background-color: #518aa3;
}

.header-text {
  background: -webkit-linear-gradient(#ffe98d, #e19f27);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.hooper-slide {
  height: 200px;
  background-color: #91B6C6;
  padding: 20px;
  margin-left: 2rem;
  display: flex;
  justify-content: center;
  align-items: center;
  color: #ffffff;
  font-size: 30px;
}

.hooper-slide:nth-child(1) {
  background: url("./../static/hytale/screenshots/9.jpg") no-repeat;
  background-size: 100%;
}

.hooper-slide:nth-child(2) {
  background: url("./../static/hytale/screenshots/8.jpg") no-repeat;
  background-size: 100%;
}

.hooper-slide:nth-child(3) {
  background: url("./../static/hytale/screenshots/9.jpg") no-repeat;
  background-size: 100%;
}

.hooper-slide:nth-child(4) {
  background: url("./../static/hytale/screenshots/10.jpg") no-repeat;
  background-size: 100%;
}

.hooper-slide:first-child {
  margin-left: 0;
}

.is-active {
  background-color: #518aa3;
}
</style>
