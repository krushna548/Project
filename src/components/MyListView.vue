<template>
    <div  class="container">
        <h1>MOVIES LIST</h1>
        <div class="columns is-multiline">
            
            <div v-for="movi in movielist" :key="movi.imdbId"  class="column is-one-third">
               <br>
               <br>
               <div  class="grid-container">
                       
                        <button > <!--v-on:click="displaySummury"-->
                            <span> <img :src="movi.Poster" style="display:inline-block" width="300" hight="400"/></span>
                        </button>
                </div>
                <h3>{{movi.Title}}</h3>
                <h3>{{movi.Type}}</h3>
                <h3>{{movi.Year}}</h3>
            </div>
        </div>
        
           
    </div>
</template>

<script>
    import axios from 'axios'
    export default {
        
    data()
    {
        return{
                movielist:undefined,
               }     
    },
    
   /* methods:
    {
        displaySummury(movi) {
            {{movi.Type}}                  
        }
    }, */
    
        mounted()
        {
            axios.get('http://www.omdbapi.com/?s=harry%20potter&apikey=e0620bd4')
            .then(Response =>{
                this.movielist=Response.data.Search
                console.warn(Response.data)
            })
        }
    }
    
</script>