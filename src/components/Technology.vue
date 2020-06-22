<template>

<div class="card my-2 tech-item">

    {{ technology}}
     <div v-on:click="deletetech" class="btn btn-del btn-danger">X</div>
   
</div>


</template>


<script>

export default {

    name: 'Technology',
    props: ['technology', 'deletetech']

}

</script>

<style>

    .tech-item{

        position: relative;
        padding: 20px 60px 20px 30px;
        font-size: 20px;
        height: 88px;
        background-color: #747779!important;
        color: white;
    }

    .btn-del {
        position: absolute;
        top: 10px;
        right: 10px;
    }

    .tech-item p{

        margin-bottom: 0!important;
    }

</style>