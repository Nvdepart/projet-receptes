<template>
    <v-container>
        <v-row v-if="article">
            <v-col cols="12" md="7">
                <h1>{{article.title}}</h1>  
                <p>{{article.body}}</p>
            </v-col>
            <v-col cols="12" md="5">
                <pre>
                    {{article}}
                </pre>
            </v-col>
        </v-row>
        <v-row v-else>
            <v-col>
                <h1>No he trobat l'article amb id {{$route.params.IdPosts}} que busques, 
                    ves a l' <nuxt-link to="/">inici</nuxt-link> o mira els altres
                    <nuxt-link to="/posts">articles</nuxt-link>
                    
                </h1>
            </v-col>
        </v-row>
    </v-container>
</template>
<script>
import posts from "@/dades/posts.js"

export default{
    mounted(){
        let id=this.$route.params.idPosts
        let post =posts.find((el)=>{
            if(id==el.id)
            {
                return true
            }
        })
        this.article=post
    },
    data(){
        return {
            article:""
        }
    }
}


</script>