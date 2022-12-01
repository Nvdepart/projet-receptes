<template>
    <v-container>
        <v-row>
            <v-col cols="12">
                <v-text-field
                v-model="textDeCerca"
                placeholder="Busca articles..."
                ></v-text-field>
            </v-col >
            <v-col cols="12" v-for="article in postsFiltrats">
                <h1>{{ article.title }} ({{article.reactions}} likes) </h1>
                <nuxt-link :to="'/posts/'+article.id">Veure article</nuxt-link>
            </v-col>
        </v-row>

        <v-row>
            <v-col cols="6">
                    {{postsFiltrats}}
            </v-col>
            <v-col cols="6">
                    {{postsDeVue}}
            </v-col>
        </v-row>

    </v-container>
</template>

<script>
import posts from "@/dades/posts.js"


export default {
    mounted(){
        this.postsDeVue= posts
    },
    data(){
        return {
            postsDeVue:[],
            textDeCerca:""
        }
    },
    computed: {
            postsFiltrats(){
                let self = this
           let filtered= this.postsDeVue.filter((el)=>{
                let titol = el.title
                if(titol.includes(self.textDeCerca)){
                    return true
                }
                    
                })
                return filtered
            }
    }
}
</script>