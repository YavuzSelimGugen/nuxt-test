<template lang="html">
  <div class="">
    <p>ID: {{id}}</p>
    <button @click='$router.go(-1)' type="button">Go Back!</button>
  </div>
</template>

<script>
export default {
  name: 'user-id',
  data: () => ({
    id: 0
  }),
  beforeMount () {
    let vm = this
    vm.id = vm.$route.params.id
    vm.loadData()
  },
  methods: {
    loadData () {
      // console.log('sss')
    }
  }
}
</script>

<style lang="css">
</style>
