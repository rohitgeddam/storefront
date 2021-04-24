<template>
  <div class="item-card">
    <div class="item-card__container">
      <div class="item-card__image">
        <img :src="item.thumbnail" alt="" />
      </div>

      <div class="item-card__body">
        <h4>{{ item.title }}</h4>
        <h5>{{ item.category }}</h5>
      </div>
    </div>


  </div>
</template>

<script>
export default {
  name: "ItemCard",
  props: {
    item: Object
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
    padding: 20px;
    max-width: 200px;
    height: auto;
    box-shadow: 0px 5px 5px 5px rgba(0,0,0,0.1);
    margin: 10px;
  }
  .item-card__container{
    display: flex;
    flex-direction: column;
  }

  .item-card__image img{
    box-shadow: 0px 5px 5px 5px rgba(0,0,0,0.1);
    width: 200px;
    height: auto;
    object-fit: cover;
  }
</style>
