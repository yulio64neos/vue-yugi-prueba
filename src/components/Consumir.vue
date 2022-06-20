<template>
  <div>
      <div v-for="item in result" :key="item.id" class="content">          
          <img v-bind:src="item.card_images[0].image_url_small">
      </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
    data: () =>({
        result: []
    }),
    created(){
        axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php")
        .then((result) =>{
            this.result = result.data.data
            console.log(result.data.data);
        });
    }
}
</script>

<style>

</style>