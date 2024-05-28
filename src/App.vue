<script>
import AppCardList from './components/AppCardList.vue';
import store from './data/store.js';

export default {
  components: {
    AppCardList
  },

  data() {
    return {
      store,
    }
  },

  methods: {
    getArchetype() {
      console.log(store.selectValue)
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype='+ store.selectValue).then(function(result) {
        console.log(result)
        store.carte = result.data.data;
    })
    },
  },

  mounted() {
    axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php').then(function(result) {
        console.log(result)
        store.archeotipi = result.data;
    })
  }
}
</script>

<template>
  <div class="container">
    <div class="row">
      <div class="col-12 text-center my-5">
        <h1>YU-GI-OH</h1>
      </div>
    </div>
  </div>
  <div class="container">
    <div class="row justify-content-center">
      <div class="col-3 mb-5">
        <select @change="getArchetype()" v-model="store.selectValue" class="form-select" name="" id="">
          <option v-for="archeotipo in store.archeotipi" :value="archeotipo.archetype_name">{{ archeotipo.archetype_name }}</option>
        </select>
      </div>
    </div>
  </div>
  
<AppCardList />
</template>

<style>

</style>