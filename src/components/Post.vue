<template>
<br> <br>
<h1 class="title" style="color: white;">{{page}}</h1>
    <div class="text" v-for="item in data" :key="item.id">
        <br>
        <div class="actual-text" >
            <h1>{{item.title}}</h1>
            <p>{{item.body}}</p>
            <img v-if="item.thumbnailUrl" :src="item.thumbnailUrl" alt="">
        </div>
        <br>
    </div>
</template>


<script>
export default{
    name: "Post",
    props: ['data', 'page']
}
</script>

<style>
    .text{
        width: 70%;
        margin: auto;
        text-align: center;
        display: flex;
        gap: 20px;
        flex-wrap: wrap;
    }
    .actual-text{
        background: #987;
        border-radius: 30px;
    }
    img{
        width: 50%;
    }
</style>


<!---
[
{
"userId": 1,
"id": 1,
"title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
"body": "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto"
},
{
"userId": 1,
"id": 2,
"title": "qui est esse",
"body": "est rerum tempore vitae\nsequi sint nihil reprehenderit dolor beatae ea dolores neque\nfugiat blanditiis voluptate porro vel nihil molestiae ut reiciendis\nqui aperiam non debitis possimus qui neque nisi nulla"
},
{
"userId": 1,
"id": 3,
"title": "ea molestias quasi exercitationem repellat qui ipsa sit aut",
"body": "et iusto sed quo iure\nvoluptatem occaecati omnis eligendi aut ad\nvoluptatem doloribus vel accusantium quis pariatur\nmolestiae porro eius odio et labore et velit aut"
}]


--->