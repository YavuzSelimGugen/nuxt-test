<template lang="html">
  <div class="">
    <p @click='$router.go(-1)'>{{title}}</p>
  </div>
</template>

<script>
export default {
  name: 'about',
  data () {
    return {
      title: 'About Page'
    }
  }
}
</script>

<style lang="css">
</style>
