<template lang="html">
  <div class="">
    <nuxt-link v-if="$i18n.locale === 'en'" :to="`/tr` + $route.fullPath" class="Header__Link" active-class="none" exact>
      {{ $t('links.tr') }}
    </nuxt-link>
    <nuxt-link v-if="$i18n.locale === 'tr'" :to="`/en` + $route.fullPath" class="Header__Link" active-class="none" exact>
      {{ $t('links.en') }}
    </nuxt-link>
    <p class="red">{{title}}</p>
    <p class="orange">{{introduction}}</p>
    <button  @click='$router.go(-1)'>Go back!</button>
    <button  @click='call'>Show message</button>
  </div>
</template>

<script>
import VueNotifications from 'vue-notifications'

export default {
  layout: 'custom-layout',
  name: 'about',
  head() {
    return {
      title: this.$t('about.title'),
      introduction: this.$t('about.introduction')
    }
  },
  data () {
    return {
      // title: 'About Page'
    }
  },
  notifications: {
     showLoginError: { // You can have any name you want instead of 'showLoginError'
       title: 'Login Failed',
       message: 'Failed to authenticate',
       type: 'error' // You also can use 'VueNotifications.types.error' instead of 'error'
     }
   },
  methods: {
    call () {
      let vm = this
      // vm.showLoginError
      this.showLoginError({title: 'my title', message: 'just an error', type: 'warn', timeout: 1000})
      // this.$q.notify({color: 'green', message: 'Item added succesfully!'})
    }
  }
}
</script>

<style lang="css">
.red {
  color: red;
}
</style>
