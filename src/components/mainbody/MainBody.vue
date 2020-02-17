<template>
    <div class='container'>
        <v-row>
            <div class='categoryBar'>
                <CategoryMenu></CategoryMenu>
            </div>
            <div class='main'>
                <!-- props: ['title', 'date', 'explain', 'stringInPicture', 'pictureSrc'], -->
                <!-- <ItemList class='ItemList'v-bind:data="ItemList"></ItemList> -->
                <ItemList v-for="(item, index) in ItemList" :key="index" v-bind:propsData="item" src='src'></ItemList>
            </div>
        </v-row>
    </div>
</template>

<script>
import CategoryMenu from '../category/CategoryMenu.vue';
import ItemList from '../items/ItemList.vue';

export default {
        data() {
            return {
                ItemList: [
                    {title: '인천', date: '2020년 2월 17일', explain: '인천 저녁노을', stringInPicture: '멋있지?', pictureSrc: "https://cdn.vuetifyjs.com/images/cards/docks.jpg"},
                    {title: '서울', date: '2020년 2월 18일', explain: '서울 저녁노을', stringInPicture: 'ㅋㅋㅋ?', pictureSrc: "https://www.bakenroll.az/en/image/cola-classic-250q.jpg"}
                ],
                src: 'https://cdn.vuetifyjs.com/images/cards/docks.jpg'
            }
        },
        components:{
            'CategoryMenu': CategoryMenu,
            'ItemList': ItemList,
        }
}
</script>

<style scoped>
    .container{
        margin: 0px 0px 0px 0px;
        padding: 0px 0px 0px 0px;
        height: 400px;
        width: 100%;
    }
    .main {
        border: 2px red solid;
        width: 75%;
        flex-wrap: wrap;
        display: flex;
    }

    .ItemList {
        width: 30%;
        height: 30%;
        margin: 0px;
        padding: 0px;
    }
    .categoryBar {
        border: 2px green solid;
        width: 25%;
    }
</style>