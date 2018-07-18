<template lang="html">
  <div class="">
    <p class="red">{{title}}</p>
    <button  @click='$router.go(-1)'>Go back!</button>
  </div>
</template>

<script>
export default {
  layout: 'custom-layout',
  name: 'about',
  data () {
    return {
      title: 'About Page'
    }
  }
}
</script>

<style lang="css">
.red {
  color: red;
}
</style>
