<template>
  <div id='app'>
    <Header></Header>
    <Search v-bind:searchQueryHistory="searchQueryHistory" 
    v-on:addSearchQueryHistory="addSearchQueryHistory"></Search>
    <Menu></Menu>
    <MainBody></MainBody>
    
  </div>
</template>

<script>
import Header from './components/common/Header.vue'
import Search from './components/search/Search.vue'
import Menu from './components/common/Menu.vue'
import MainBody from './components/mainbody/MainBody.vue'

export default {
  name: 'App',
  components: {
    'Header': Header,
    'Search': Search,
    'Menu': Menu,
    'MainBody': MainBody,
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

<style scoped>
    
</style>