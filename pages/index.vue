<template>
  <section class="container">
    <div>
      <app-logo/>
      <h1 class="title">
        nuxt-v2
      </h1>
      <h2 class="subtitle">
        Nuxt.js project
      </h2>
      <div class="links">
        <nuxt-link to="/about">About page</nuxt-link>
        <br>
        <nuxt-link to="/user/10">User ID</nuxt-link>
        <div v-for="(user) in visatypes" :key="user.ID" class="">
          <nuxt-link :to="'/user/'+user.ID">{{ user.name }}</nuxt-link>
        </div>
          <button @click="eventa">sss</button>
      </div>
    </div>
  </section>
</template>

<script>
import AppLogo from '~/components/AppLogo.vue'

export default {
  components: {
    AppLogo
  },
  data () {
    return {
      visatypes: []
    }
  },
  beforeMount () {
    this.loadData()
  },
  methods: {
    eventa () {
      // console.log('sss')
      this.showLoginError()
    },
    loadData () {
      this.visatypes = [{name : 'Yavuz', ID: 1}]
      this.visatypes.push({name : 'Yavuz2', ID: 2})
      this.visatypes.push({name : 'Yavuz3', ID: 3})
      // this.visatypes += {name : 'Yavuz2', ID: 2}
      // this.visatypes += {name : 'Yavuz3', ID: 3}
      // console.log(this.visatypes)
    }
  },
  notifications: {
    showLoginError: { // You can have any name you want instead of 'showLoginError'
      title: 'Hata Basligi',
      message: 'Hata icerigi',
      type: 'error' // You also can use 'VueNotifications.types.error' instead of 'error'
    }
  }
}
</script>

<style>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
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
