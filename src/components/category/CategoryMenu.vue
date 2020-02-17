<template>
   <v-card
    height="500"
    width="256"
    class="mx-auto"
  >
    <v-navigation-drawer permanent>
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="title">
            메뉴
          </v-list-item-title>
          <v-list-item-subtitle>
            카테고리
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense nav>
        <v-list-item class='listItem'
          v-for="item in items"
          :key="item.title"
          link
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </v-card>
</template>

<script>
export default {
    data() {
        return {
            items: [
                {title: '전체', icon: "fas fa-search-plus"},
                {title: '가전', icon : "fas fa-tv"},
                {title: '의류', icon : "fas fa-tv"},
                {title: '게임', icon : "fas fa-tv"},
                {title: '스포츠', icon : "fas fa-tv"},
                {title: '자동차', icon : "fas fa-tv"},
                {title: '도서', icon : "fas fa-tv"},
                {title: '여행', icon : "fas fa-tv"},
            ]
        }
    }
}
</script>

<style scoped>
    .v-list-item__title {
        padding-left: 20px;
    }
    
</style>