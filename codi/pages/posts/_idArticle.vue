<template>
    <v-container>
       <h1>Article</h1>
                    <v-row v-if="article">
                        <v-col cols="9" md="2">
                            <h1> {{article.title}}</h1> 
                            <p>{{article.body}}</p>     
                        </v-col>
                        <v-col cols="3" md="2">
                            <pre>
                                {{article}}
                            </pre>
                        </v-col>
                    </v-row>
                    <v-row v-else>
                        <v-col>
                            <h1>No he trobat l'article amb id <strong>{{$route.params.idArticle}}</strong> que busques,
                                ves a l'<nuxt-link to="/">inici</nuxt-link> o mira els altres <nuxt-links to="/posts">
                                articles</nuxt-links>
                            </h1>
                        </v-col>
                    </v-row>
    </v-container>
</template>

<script>
import posts from '@/dades/posts.js'

export default{

    mounted(){
        let id = this.$route.params.idArticle
        // Buscar el article 
        // var self = this
       let post = posts.find((el) => {
            if(id==el.id){
                // Hem trobat el article
                // self.el = article
              return  true
            }
        })
       this.article = post
    },
    data(){
        return {
            article:{}
        }
    }
   
}

</script>