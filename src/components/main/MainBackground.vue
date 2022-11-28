<template>
    <div class="bg-color d-flex flex-wrap align-items-center justify-content-center">
      <div class="w-100">
        <select name="albums"  v-model="value">
        <option></option>
        <option v-for="(element) in arraigenre" :key="element" :value="element">{{element}}</option>
      </select>
      </div>
      
       <ContentCard v-for="(elem,index) in search " :key="index" :get="elem"/>
       
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
            info:[],
            arraigenre:[],
            value:"",
        }
       },
       mounted(){

           this.arrai()
        },

        computed:{
          search(){
            if(this.value==""){
              return this.info
            }else{
              return this.info.filter((element)=>{
                return element.genre == this.value
              })
            }
            
          }
        },
       
       methods:{
         arrai(){
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
          .then((response) => {
            this.info = response.data.response
            
            this.info.forEach(element => {

              if(!this.arraigenre.includes(element.genre))
              this.arraigenre.push(element.genre)
            });
          
            
            });

            
        }},
      
      
       }
       
      
</script>

<style lang="scss" scoped>
        .bg-color{
            height: 100vh;
            gap:10px;
            background-color: #1E2D3B;
            
        }
</style>