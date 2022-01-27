<template>
  <main>
    <div class="search">
      <input type="text" v-model="search">
    </div>
    <NewsList v-bind:news="filterNews"/>
  </main>
</template>

<script>
import NewsList from '@/components/NewsList'



export default {
  name: 'App',
  data(){
    return {
      news: [
        {title: 'Срочная новость!', info: 'Сосу жопу'},
        {title: '12 апреля день Космонавтики', info: 'Запустят салюты'},
        {title: 'ЧП на станции Кунцево', info: 'Очевидцы рассказаывают о бомбе'},
        {title: 'Комета пролетит', info: 'Говорят, что сегодня она пролетит'},
      ],
      search: "",
    }
  },
  components: {
    NewsList
  },
  computed: {
    filterNews() {
      var newsArray = this.news,
      searchString = this.search;

      if(!searchString) {
        return newsArray;
      }

      searchString = searchString.trim().toLowerCase();

      newsArray = newsArray.filter(function(item){
        if(item.title.toLowerCase().indexOf(searchString) !== -1){
          return item;
        }
      })
      return newsArray;
    } 
  }
}
</script>

<style>
  *{
    box-sizing: border-box;
    margin: 0;
  }
  body {
    background-color: #ebebeb;
    font-family: sans-serif;
  }
  .search{
    display: flex;
    justify-content: center;
    padding: 30px;
    background-color: #2fffff;
  }
  .search input {
    padding: 15px;
    width: 500px;
    border-radius: 10px;
    border: none;
    outline: none;
    font-size: 20px;
    font-weight: bold;

  }
</style>
