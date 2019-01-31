<template>
  <div>
    <div class="carousel-container">
      <h1>Популярное</h1>
      <div class="preview-popular">
        <h2>Вариативные отношения Hytale</h2>
      </div>
      <div class="preview-popular-mini">
        <div class="preview-mini">
          <h3>Серверные настройки</h3>
        </div>
        <div class="preview-mini">
          <h3>Графика в Hytale</h3>
        </div>
      </div>
    </div>
    
    <div class="carousel-container">
      <div class="carousel-text-header">
        <h2>Моды</h2>
        <nuxt-link to="/mods">Показать всё...</nuxt-link>
      </div>
      <hooper :items-to-show="3.5" :items-to-slide="1" :wheelControl="false" class="carousel">
        <slide v-for="(slide, key) in carousels[0]" :key="key">
          {{ slide.name }}
        </slide>
        <hooper-navigation slot="hooper-addons" />
      </hooper>
    </div>

    <div class="carousel-container">
      <div class="carousel-text-header">
        <h2>Карты</h2>
        <nuxt-link to="/maps">Показать всё...</nuxt-link>
      </div>
      <hooper :items-to-show="3.5" :items-to-slide="1" :wheelControl="false" class="carousel">
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

<style scoped>
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
  height: 30rem;
  width: 45rem;
  background: url("./../static/images/media/screenshots/1-thumb.jpg") no-repeat;
  background-size: 100%;
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

.hooper-slide:first-child {
  margin-left: 0;
}

.is-active {
  background-color: #518aa3;
}
</style>
