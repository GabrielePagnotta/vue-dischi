<template>
    <div class="bg-color d-flex flex-wrap align-items-center">
       <ContentCard v-for="(elem,index) in info " :key="index" :get="elem"/>
       
    </div>
</template>

<script>
import ContentCard from "../main/ContentCard.vue"
import axios from "axios"
    export default {
        name:"MainBackground",
        components:{
            ContentCard,
       },
       data(){
        return{
            info:""
        }
       },
       mounted(){
        
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
          .then((response) => {
            this.info = response.data.response
          })
        },
       
       methods:{
        
      },
       }
      
</script>

<style lang="scss" scoped>
        .bg-color{
            width: 100vw;
            height: 100vh;
            gap:10px;
            background-color: #1E2D3B;
            
        }
</style>