<template>

<div class="header-top">
    <p>{{ title }}</p>
</div>


</template>


<script>

export default {

    name: 'Contenu',

    data(){
        
        return {

            title: 'List of technologies that i use actually : I am a fullstack software engineer.',
        }  
    },

    methods: {

    },
        
    components: {

       
    }

}

</script>

<style scoped>

.header-top{

    position: fixed;
    top: 0;
    height: 50px;
    background: #333;
    width: 100%;
    text-align: center;
    line-height: 50px;
    font-size: 25px;
    color:white;
}


</style>