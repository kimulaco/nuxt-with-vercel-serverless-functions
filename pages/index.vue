<template>
  <div class="container">
    <div>
      <logo />
      <h1 class="title">
        nuxt-with-vercel-serverless-functions
      </h1>
      <h2 class="subtitle"></h2>
      <div class="links">
        <button
          type="button"
          class="button--green"
          @click="handleClickStaticAPI"
        >
          Static API
        </button>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import axios from 'axios'
import Logo from '~/components/Logo.vue'

export default Vue.extend({
  components: {
    Logo
  },
  methods: {
    handleClickStaticAPI() {
      axios.get('/api/test').then((response) => {
        console.log(response.data)
      })
    }
  }
})
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
  font-size: 50px;
  color: #35495e;
  margin: 20px 0 0;
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
