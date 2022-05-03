<template>

  <div class="menu">
    <br>
    <div class="left-div">
      <h1 class="title">FAKERY COMPANY</h1>
    </div> <br> <br>
    <div class="right-div">
      <div class="link-container">
        <p class="pmenu" @click="postPage">Posts</p>
        <p class="pmenu" @click="albumPage">Albums</p>
        <p class="pmenu" @click="photosPage">Photos</p>
        <p class="pmenu">Todos</p>
        <p class="pmenu">Users</p>
      </div>
    </div>
    <br> <br> <br>
  </div> <br> <br> <br>
  <Loading v-if="available"/>
  <div class="content" v-else>
    
    <Post :data="data" :page="page"/>

  </div>

</template>

<script>
import image from '../src/assets/Spin-1s-200px.gif'
import Post from './components/Post.vue'
import axios from 'axios'
import Loading from './components/Loading.vue'
import Albums from './components/Albums.vue'
export default{
    name: "App",
    props: {},
    methods: {},
    data() {
        return {
            data: null,
            available: true,
            image,
            postData: null,
            albumData: null,
            page: 'posts',
            photosData: null
        };
    },
    components: { Post, Loading, Albums },
    mounted(){
      axios.get('https://jsonplaceholder.typicode.com/posts').then(res => {this.data = res.data; this.available = false; this.postData = res.data})
      axios.get('https://jsonplaceholder.typicode.com/albums').then(res => {this.albumData = res.data; this.available = false})
      axios.get('https://jsonplaceholder.typicode.com/photos').then(res =>{this.photosData = res.data; this.available = false})
    },
    methods: {
      postPage(){
        this.data = this.postData;
        this.page = 'posts'
      },
      albumPage(){
        this.data = this.albumData,
        this.page = 'album'
      },
      photosPage(){
        this.data = this.photosData;
        this.page = 'photos'
      }
    },
}
</script>

<style>
*{
  margin: 0;
}
.menu{
  width: 80%;
  background: #090ca798;
  margin: auto;
  border-bottom-right-radius: 30px;
  border-bottom-left-radius: 30px;
}
.title{
  margin-top: 30px;
  font-size: 50px;
  text-align: center;
}
.link-container{
  width: 70%;
  display: flex;
  flex-wrap: wrap;
  gap: 50px;
  font-size: large;
  color: white;
  margin: auto;
  text-align: center;
}
.pmenu{
  background: #6789;
  padding: 15px;
  transition: 0.5s ease-in;
  cursor: pointer;
}
.pmenu:hover{
  background: #678957;
  border-left: 2px white solid;
}
.content{
  width: 90%;
  background: #678965;
  margin: auto;
  border-radius: 30px;
}
.loading{
  background: #24262482;
  margin: auto;
  border-radius: 0px;
  width: 100%;
  height: 100%;
  font-size: larger;
  text-align: center;
  position: fixed;
  top: 0px;
  height: fit-content;
}
.loading p{
  font-size: larger;
  color: white;
  margin-top: 10px;
}
img{
  width: 5%;
  height: auto;
}
</style>
