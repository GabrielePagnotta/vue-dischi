<template>
    
<div class="box d-flex">
    <div class="col">
       <div class=" underbox1 d-flex justify-content-center">
        <div class="imagebox image-fluid">
            <img class="image-fluid" :src="get.poster" alt="">
        </div>
        </div>
        <div class=" underbox2 ">
        <h2 class="text-light mt-2">{{get.title}}</h2>
        <h3 class="text-light mt-4">{{get.author}}</h3>
        <h3 class="text-light">{{get.genre}}</h3>
        <h3 class="text-light">{{get.year}}</h3>
        </div> 
</div>
    
</div>

</template>

<script>
    export default {
        name:"ContentCard",
       props:{
        get: Object,
       }
    }
    
</script>

<style lang="scss" scoped>
    
.box{
    width:calc(100% / 5 - 10px);
    height:500px;
    background-color: #2E3A46;
    
}
.underbox1{
    height:60%;
}
.underbox2{
    height:40%;
}

.imagebox{
    width:80%;
    height:100%;
    aspect-ratio: 1/1;
    
}

img{
    width:70%;
}
    
</style>