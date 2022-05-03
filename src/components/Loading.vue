<template>
        <div class="loading">
      <img :src="image" alt="text">
      <p>LOADING.....</p> <br>
  </div>
    
</template>

<script>
import image from '../assets/Spin-1s-200px.gif'

export default{
    name: "Loading",
    data(){
        return{
            image
        }
    }
}
</script>