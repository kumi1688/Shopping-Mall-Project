<template>
  <v-form @submit.prevent="onSubmitSearchQuery">
    <v-container class='container'>
          <v-text-field 
            v-model="searchQuery"
            label="검색어 입력"
            solo
          ></v-text-field>
          <h1 @click='onSubmitSearchQuery'><i class="fas fa-search"></i></h1>
    </v-container>
  </v-form>
</template>

<script>
export default {
    data(){
        return{
            searchQuery : '',
        }
    },
    props: ['searchQueryHistory'],
    methods: {
        onSubmitSearchQuery(){
            if(this.searchQuery !== ''){
                let newSearchQuery = this.searchQuery && this.searchQuery.trim();
                this.$emit('addSearchQueryHistory', newSearchQuery);
                this.searchQuery = '';
            }
        }
    },
}
</script>

<style scoped>
    .container{
        display: flex;
    }
    h1 {
        padding-left: 10px;
        margin-top: 5px;
    }
    div {
        text-align : center;
    }
</style>

