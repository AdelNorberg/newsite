<template>
  <div class="default-layout">
    <div class="container">
      <header class="header">
        <div class="header-kweebec"></div>
        <div class="header-text">Kweebec</div>
      </header>
      <nav class="nav-bar">
        <div>
          <nuxt-link to="/">
            <home class="home-icon nav-bar-list" />
          </nuxt-link>
          <nuxt-link v-for="(item, key) in routers" :to="'/' + item.router" :key="key" class="nav-bar-list">{{ item.name }}</nuxt-link>
        </div>
        <div class="sign-button"><nuxt-link to="sign" class="sign">Войти</nuxt-link></div>
      </nav>
      <nuxt />
      <footer class="footer">Footer</footer>
    </div>
  </div>
</template>

<script>
import home from "../assets/home.vue"

export default {
  components: {
    home
  },
  data() {
    return {
      routers: [
        { name: 'Моды', router: 'mods' },
        { name: 'Карты', router: 'maps' },
        { name: 'Сборки', router: 'assembly' },
        { name: 'Текстуры', router: 'textures' }
      ]
    }
  }
}
</script>

<style lang="scss">
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

h1, h2, h3, h4, .footer, .header, .nav-bar {
  color: white;
}


.default-layout {
  display: flex;
  justify-content: center;
  min-width: 1440px;
  background: url("./../static/Hytale/bg.webp") no-repeat, url("./../static/Hytale/footer.webp") no-repeat;
  background-size: 115%;
}

.container {
  width: 1440px;
  padding: 0 20px 0 20px;
}

.header {
  height: 100px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 50px;
  margin-top: 4rem;
  margin-bottom: 1rem;
  font-weight: 700;
}

.header-kweebec {
  height: 8rem;
  width: 10rem;
  background: url("./../static/images/kweebec.png") no-repeat;
  background-size: 100%;
}

.header-text {
  margin-right: 6rem;
}

.nav-bar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 3.5rem;
  background-color: #1b304f;
  font-size: 25px;
  box-shadow: 0 4px 30px rgba(0, 0, 0, 0.5), inset 0 0 0 2px #4e5765;
  border-radius: 5px;
  position: relative;
  border: 2px solid #15243a;
  // :before {
  //   top: 0;
  //   left: 0;
  //   position: absolute;
  //   content: "";
  //   display: block;
  //   width: 14px;
  //   height: 14px;
  //   background: url("./../static/images/container-corner.png") no-repeat 0 0;
  //   background-size: 14px;
  //   transform: rotate(180deg);
  // }
  // :after {
  //   top: 0;
  //   right: 0;
  //   position: absolute;
  //   content: "";
  //   display: block;
  //   width: 14px;
  //   height: 14px;
  //   background: url("./../static/images/container-corner.png") no-repeat 0 0;
  //   background-size: 14px;
  //   transform: rotate(-90deg);
  // }
}

.nav-bar-list {
  padding-left: 0.9rem;
  color: #a5b9c6;
  :hover {
    color: #edb548;
  } 
}

.home-icon {
  height: 1.5rem;
  padding-top: 0.2rem;
}

.sign-button {
  display: inline-block;
  position: relative;
  font-weight: 600;
  z-index: 0;
  height: 1.7em;
  padding: 0.1rem 1.2em 0 1.2em;
  margin-right: 0.2rem;
  border-radius: 5px;
  border: 1px solid #a17f3c;
  background: linear-gradient(to bottom, #3583b4, #225b8b);
  box-sizing: border-box;
  box-shadow: inset 0 0 0 2px rgba(0, 0, 0, 0.3);
}

.footer {
  height: 100px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 20px;
  margin-top: 2rem;
  margin-bottom: 1rem;
  background-color: #10161E;
  box-shadow: inset 0 0 0 1px #2c2b22;
}
</style>
