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
    <div class="mt-3 textbox text-center">
        <h5>{{ title }}</h5>
    </div>
    <div class="mt-2 d-flex justify-content-center">
        <span>{{ archetype }}</span>
    </div>
</div>
</template>

<style scoped>

img {
    width: 100%;
}

.textbox {
    width: 100%;
    height: 5rem;
}
</style>