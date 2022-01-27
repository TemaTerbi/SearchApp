<template>
  <div class="newsList__wrapper">
    <div class="newsList__news news">
      <div class="news__name">
        {{news.title}}
      </div>
      <div class="news__info">
        <p>
          {{news.info}}
        </p>
      </div>
    </div>
  </div>
</template>


<script>
  export default {
    props: {
      news: {
        type: Object,
        require: true
      }
    },
    watch: {

    }
  }
</script>


<style scoped>
  .news{
    padding: 20px;
    background-color: white;
    font-size: 20px;
    border-radius: 10px;
    min-width: 500px;
    margin-bottom: 1rem;
  }
  .news__name{
    font-weight: bold;
    font-size: 30px;
    margin-bottom: 1rem;
  }
</style>