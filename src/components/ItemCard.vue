<template>
<router-link :to="{ name: 'ItemDetail', params: { 'id': id}}" class="item-link">
  <div class="item-card">
    <div class="item-card__container">
      <div class="item-card__image">
        <img :src="item.thumbnail" alt="" />
      </div>

      <div class="item-card__body">
        <h3>{{ item.title }}</h3>
        <h4 class="item-card__pill">{{ item.category }}</h4>
      </div>
    </div>
    </div>
</router-link>
</template>

<script>
export default {
  name: "ItemCard",
  props: {
    item: Object,
    id: Number,
  },
  data(){
    return {
      
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .item-card{
    /* padding: 20px; */
    max-width: 400px;
    height: auto;
    box-shadow: 0px 5px 5px 5px rgba(0,0,0,0.1);
    margin: 20px;
  }
  .item-card:hover {
    transform: scale(1.1);
    cursor: pointer;
  }
  .item-card__container{
    display: flex;
    flex-direction: column;
  }

  .item-card__image img{
    box-shadow: 0px 5px 5px 5px rgba(0,0,0,0.1);
    width: 300px;
    height: auto;
    object-fit: cover;
  }

  .item-link{
    color: gray;
    text-decoration: none;
  }

  .item-card__body{
    display:flex;
    flex-direction: column;
    align-items: center;
  }

  .item-card__pill{
    background: gray;
    color: white;
    width: 50%;
    border-radius: 20px;
  }
</style>
