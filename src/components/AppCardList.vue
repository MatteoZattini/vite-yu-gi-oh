<script>
import AppSingleCard from './AppSingleCard.vue';
import store from '../data/store.js';

export default {
    name: "AppCardList",

    components: {
        AppSingleCard
    },

  data() {
    return {
        store,
    }
  },

  methods: {

  },

  mounted() {
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0').then(function(result) {
        console.log(result)
        store.carte = result.data.data;
    })
  }
}
</script>

<template>
    <div class="container">
        <div class="row">
            <div class="col-12 d-flex flex-wrap">
                    <div class="my-card" v-for="carta in store.carte"> 
                        <AppSingleCard :img="carta.card_images[carta.card_images.length - 1].image_url" :title="carta.name" :archetype="carta.archetype" />
                    </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.my-card {
    width: calc(100% / 5 - 2rem);
    margin-bottom: 3rem;
    margin-left: 1rem;
    margin-right: 1rem;
}

</style>