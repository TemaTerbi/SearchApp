<template>
  <div class="newsList">
    <News v-for="news in news" :key="news.news" v-bind:news="news"/>
  </div>
</template>

<script>
import News from '@/components/News'

export default {
  props: ['news'],
  components: {
    News
  }
    
}
</script>

<style scoped>
  .newsList{
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 30px;
  }
</style>
