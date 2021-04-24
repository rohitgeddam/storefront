<template>
  <div class="container">
    <h1>New Arrivals</h1>
    <ItemCard v-for="item in items" :key="item.id" :item="item"/>

  </div>
</template>

<script>
// @ is an alias to /src
import ItemCard from "@/components/ItemCard.vue";
import ItemService from "@/services/ItemService.js"

export default {
  name: "Home",
  components: {
    ItemCard,
  },

  data(){
    return {
      items: null
    }
  },

  created(){
    ItemService.getItems()
    .then(res => {
      this.items = res.data
    })
    .catch(err => {
      console.log("err", err)
    })
  }

};
</script>

<style scoped>
  .container{
    display: flex;
    /* justify-content: center; */
    align-items: center;
    flex-direction: column;
  }
</style>
