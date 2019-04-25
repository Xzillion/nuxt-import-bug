<template>
  <section class="container">
    <div>
      <logo />
      <h1 class="title">
        nuxt-import-bug
      </h1>
      <h2 class="subtitle">
        My tiptop Nuxt.js project
      </h2>
      <div class="links">
        <a
          href="https://nuxtjs.org/"
          target="_blank"
          class="button--green"
        >Documentation</a>
        <a
          href="https://github.com/nuxt/nuxt.js"
          target="_blank"
          class="button--grey"
        >GitHub</a>
      </div>
    </div>
  </section>
</template>

<script>
import Logo from '~/components/Logo.vue'
import isDate from 'date-fns/is_date'

// custom function, as same as date-fns/is_date
function isDate2 (argument) {
  return argument instanceof Date
}
export default {
  components: {
    Logo
  },
  created () {
    const date = new Date();
    // in dev environment, print: true false
    // in prod environment, print: true true
    // in browser console, print: true true
    console.log(isDate2(date), 'custom function')
    console.log(isDate(new Date()), 'import date-fns util function')
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
