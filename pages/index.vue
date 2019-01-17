<template>
  <div>
    <ul>
      <li><nuxt-link :to="{name: 'index'}">HOME</nuxt-link></li>
      <li><nuxt-link :to="{name: 'about'}">ABOUT</nuxt-link></li>
      <li><nuxt-link :to="{name: 'news', params: {newsId: 3306}}">NEWS</nuxt-link></li>
      <li><nuxt-link :to="{name: 'ansyData', query: {id: queryArray[0]}}">ansyData1</nuxt-link></li>
      <li><nuxt-link :to="{name: 'ansyData', query: {id: queryArray[1]}}">ansyData2</nuxt-link></li>
    </ul>
  </div>
</template>
 
<script>
import axios from 'axios'
export default {
  created() {
    console.log(this.queryArray)
  },
  async asyncData(context) {
    let { data } = await axios.get(`https://api.myjson.com/bins/17px7y`)
    return { queryArray: data.queryArray }
  }
}
</script>
 
<style>
</style>
