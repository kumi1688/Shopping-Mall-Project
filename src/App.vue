<template>
  <div id='app'>
    <Header></Header>
    <Search v-bind:searchQueryHistory="searchQueryHistory" 
    v-on:addSearchQueryHistory="addSearchQueryHistory"></Search>
    <Category></Category>
  </div>
</template>

<script>
import Header from './components/common/Header.vue'
import Search from './components/search/Search.vue'
import Category from './components/category/Category.vue'

export default {
  name: 'App',
  components: {
    'Header': Header,
    'Search': Search,
    'Category': Category
  },

  data: () => ({
    searchQueryHistory: [],
  }),
  created() {
    if(localStorage.length > 0 ){
                for(var i = 0; i < localStorage.length; i++){
                    this.searchQueryHistory.push(localStorage.key(i));
                }
            }
  },
  methods: {
    addSearchQueryHistory(newQuery){
      localStorage.setItem(localStorage.length+1, newQuery);
      this.searchQueryHistory.push(newQuery);
    }
  },
};
</script>
