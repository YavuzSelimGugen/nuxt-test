<template lang="html">
  <div class="">
    <!-- {{title}} -->
    <div v-for="i in title" :key="i.id" class="center">
      {{i.name}}
    </div>
  </div>

</template>

<script>
import axios from 'axios'
export default {
  async asyncData ({ params }) {
    let { data } = await axios.get(`https://sheetsu.com/apis/v1.0su/ae6bb5a37f9b`)
    console.log(data)
    // list = data
    return { title: data }
  },
  data () {
    return {
      list: []
    }
  }
}
</script>

<style lang="css">
.center {
  text-align: center;
}
</style>
