<template>
    <div>
        <v-card
    class="mx-auto"
    max-width="400"
  >
    <v-img
      class="white--text align-end"
      height="200px"
      src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
    >
    <!-- "https://cdn.vuetifyjs.com/images/cards/docks.jpg" -->
      <v-card-title>{{propsData.stringInPicture}}</v-card-title>
    </v-img>

    <v-card-subtitle class="pb-0">{{propsData.date}}</v-card-subtitle>

    <v-card-text class="text--primary">
      <div>{{propsData.title}}</div>

      <div>{{propsData.explain}}</div>
    </v-card-text>

    <v-card-actions>
      <v-btn
        color="orange"
        text
      >
        장바구니
      </v-btn>

      <v-btn
        color="orange"
        text
      >
        구매
      </v-btn>
    </v-card-actions>
  </v-card>
    </div>
</template>

<script>

export default {
    data() {
        return{
          pictureSrc : propsData.pictureSrc,  
        }
    },
    props: ['propsData', 'src'],
    computed: {
        pictureSrc() {
            return propsData.pictureSrc
        }
    },
    created() {
        console.log(this.propsData);
    },

}
</script>

<<style >
    
</style>