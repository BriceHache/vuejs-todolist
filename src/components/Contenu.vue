<template>

<div class="container mt-5">

        <h1>{{ msg }} <span>&nbsp;({{numberoftechs()}})</span> </h1>

       
        <form>

            <div class="form-group col-lg-12 col-md-12 technologies mt-3">

                <label for="technology" class="col-lg-3 col-md-3 col-sm-12 col-sx-12">
                    Technology :
                </label>

                <input v-model="formData.technology" type="text" name="technology" id="technology" class="form-control col-lg-9 col-md-9 col-sm-12 col-sx-12">
    
            </div>

             <button v-on:click.prevent="createTech" class="btn btn-primary my-3 tech-todo"> Add technology</button>
            
        </form>

         <div class="mt-5">

                <ul>
                    <li v-bind:key="index" v-for="(technology, index) in listoftechnologies ">

                        <technology v-bind:id="index" :technology="technology" :deletetech="deletetech" ></technology>
                    </li>
                </ul>

            </div>

</div>


</template>


<script>

import Technology from './Technology.vue'
import Swal from 'sweetalert2'

export default {

    name: 'Contenu',

    data(){
        
        return {

            msg: 'todo list',

            formData: {
                
                technology: ''
            },

            listoftechnologies : ['Javascript','Php', 'Java', 'C#' ,
            'Laravel', 'Asp.net mvc', 'Angular', 'Vue js', 'jQuery', 'Ionic', 'Flutter', 'Docker', 'Git']
        }  
    },

    methods: {

        createTech: function(){

            if(this.formData.technology.length < 2){
                Swal.fire({
                    title: 'Error',
                    text: 'your technology name must have at least 2 characters !',
                    icon: 'error',
                    showCancelButton: true,
                    showConfirmButton: false,
                    cancelButtonText: 'OK'
                    })
            }else{

                    this.listoftechnologies.push(this.formData.technology)
                    this.formData.technology = ''
            }

        }, 

        deletetech: function(e){

            this.listoftechnologies.splice(e.target.parentNode.id, 1)
        },
        numberoftechs: function(){

            return this.listoftechnologies.length

        }
    },
        
    components: {

       'technology': Technology
    }

}

</script>

<style>

    h1{
        margin-top: 100px!important;
        text-transform: uppercase;
        text-align: center;
    }

    h1 span {
        color : green;
    }

    ul{
        list-style-type: none;
        padding: 0;
    }

    .technologies{
        display: flex;
    
    }

    label{
        font-size: 28px;
    }
    

</style>