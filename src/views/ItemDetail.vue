<template>
    <div v-if="item" class="item-detail">
        <div class="container">
          <div class="info">
            <div class="thumbnail">
              <img :src="item.thumbnail" />
            </div>

            <div class="details">
              <p><b>Title - </b>{{item.title}}</p>
              <p><b>Description - </b>{{item.description}}</p>
              <p><b>Color - </b>{{item.color}}</p>
              <p><b>Price - </b>{{item.price}}</p>
              <p v-if="item.available" class="details__available">Available</p>
              <p v-else class="details__notavailable">Not Available</p>
            </div>
          </div>

          <div class="more-images">
        
              <img v-for="image in item.images" :key="image.length*10" :src="image" alt=""/>
           
          </div>
          
        </div>
    </div>

</template>


<script>
import ItemService from '@/services/ItemService'

export default {
  name: "ItemDetail",
  components: {
    
  },
  props: ['id'],

  data(){
    return {
      item: null,
      available: true,
    }
  },

  created(){
    ItemService.getItem(this.id)
    .then(res => {
      this.item = res.data
    })
    .catch(err => {
      console.log("err", err)
    })
  }

};
</script>


<style>
.container{
  display: flex;
  flex-direction: column;
  align-items: center;
}

.thumbnail{
}

.thumbnail img {
  width: 300px;
  height: auto;
}

.info{
  display: flex;
  justify-content: center;
  box-shadow: 0px 5px 5px 5px rgba(0,0,0,0.1);
}

  @media only screen and (max-width: 600px){
    .info {
      flex-direction: column;
    }
  }

.details{
  display: flex;
  flex-direction: column;
  min-width: 200px;
  padding: 24px;
  align-items: flex-start;
}
.details__available{
  padding: 10px;
  background: green;
  border-radius: 20px;
  width: 90%;
  color: white;
  font-size: 18px;
}

.details__notavailable{
  padding: 10px;
  background: red;
  border-radius: 20px;
  width: 90%;
  font-size: 18px;
  color: white;
}

.more-images{
  margin-top: 24px;
}

.more-images img{
  margin: 20px;
  width: 300px;
  height: 300px;
}


</style>