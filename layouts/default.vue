<template>
  <div class="default-layout">
    <div class="container">
      <header class="header">
        <div class="header-kweebec"></div>
        <div>Kweebec</div>
      </header>
      <nav class="nav-bar">
        <div>
          <nuxt-link v-for="(item, key) in routers" :to="'/' + item.router" :key="key" class="nav-bar-list">{{ item.name }}</nuxt-link>
        </div>
        <div>Войти</div>
      </nav>
      <nuxt />
      <footer class="footer">Footer</footer>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      routers: [
        { name: 'Главная', router: '' },
        { name: 'Моды', router: 'mods' },
        { name: 'Карты', router: 'maps' },
        { name: 'Сборки', router: 'assembly' },
        { name: 'Текстуры', router: 'textures' }
      ]
    }
  }
}
</script>


<style>
html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
  background-color: #10233F;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

a {
  color: white;
  text-decoration: none;
}

a:hover, h1, h2, h3, h4, .footer, .header, .nav-bar {
  color: white;
}


.default-layout {
  display: flex;
  justify-content: center;
}

.container {
  width: 1440px;
}

.header {
  height: 100px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 50px;
}

.header-kweebec {
  height: 5rem;
  background: url("./../static/images/kweebec.png") no-repeat;
  background-size: 100%;
}

.footer {
  margin-top: 2rem;
  margin-bottom: 1rem;
}

.nav-bar {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  height: 50px;
  background-color: #91B6C6;
  font-size: 25px;
}

.nav-bar-list {
  padding: 0 0 0 0.8rem;
}

.footer {
  height: 100px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 20px;
  background-color: #91B6C6;
}
</style>
