<script>
export default {
    name: "AppSingleCard",

    props: {
        img: String,
        title: String,
        archetype: String
    },

  data() {
    return {

    }
  },

  methods: {

  },

  mounted() {
    
  }
}
</script>

<template>
<div>
    <div>
        <img :src="img" alt="">
    </div>
    <div>
        <h3>{{ title }}</h3>
    </div>
    <div>
        <span>{{ archetype }}</span>
    </div>
</div>
</template>

<style>
</style>