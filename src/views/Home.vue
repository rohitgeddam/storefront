<template>
  <div class="container">
    <ItemCard v-for="item in items" :key="item.id" :item="item"/>

  </div>
</template>

<script>
// @ is an alias to /src
import ItemCard from "@/components/ItemCard.vue";

export default {
  name: "Home",
  components: {
    ItemCard,
  },

  data(){
    return {
    items: [
      {
        id: 1,
        category: 'saree',
        title: 'Designer Saree',
        description: 'Indian Saree',
        color: 'black',
        price: 20.99,
        thumbnail: "https://i.imgur.com/8PAWlEd.jpeg",
        images: [
          "https://i.imgur.com/8PAWlEd.jpeg",
          "https://assets.panashindia.com/media/catalog/product/cache/1/small_image/262x377/9df78eab33525d08d6e5fb8d27136e95/2/4/2497sr03-463.jpg"
        ]
      },

      {
        id: 1,
        category: 'saree',
        title: 'Designer Saree',
        description: 'Indian Saree',
        color: 'black',
        price: 20.99,
        thumbnail: "https://i.imgur.com/8PAWlEd.jpeg",
        images: [
          "https://i.imgur.com/8PAWlEd.jpeg",
          "https://assets.panashindia.com/media/catalog/product/cache/1/small_image/262x377/9df78eab33525d08d6e5fb8d27136e95/2/4/2497sr03-463.jpg"
        ]
      },

      {
        id: 1,
        category: 'saree',
        title: 'Designer Saree',
        description: 'Indian Saree',
        color: 'black',
        price: 20.99,
        thumbnail: "https://i.imgur.com/8PAWlEd.jpeg",
        images: [
          "https://i.imgur.com/8PAWlEd.jpeg",
          "https://assets.panashindia.com/media/catalog/product/cache/1/small_image/262x377/9df78eab33525d08d6e5fb8d27136e95/2/4/2497sr03-463.jpg"
        ]
      },
    ]
    }
    
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
