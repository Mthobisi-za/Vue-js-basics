<template>
   <Loading v-if="isDataAvailable"/>
    <div v-else>
        
    </div>
</template>

<script>
import Loading from './Loading.vue'

    export default{
  components: { Loading },
        name: "Albums",
        props:['data'],
        data(){
            return{
                data: null,
                isDataAvailable: true
            }
        },

    }
</script>
<style>

</style>