<template>
    <v-container>
        <v-row>
            <v-col cols="12"></v-col>
            <v-col cols="12" v-for="article in postsDeVue">
                <h2>{{article.title}} ({{article.reactions}} like)</h2>
                <nuxt-link :to="'/posts/'+ article.id">Veure article</nuxt-link>
                <pre>
                    {{article}}
                </pre>
            </v-col>
        </v-row>
    </v-container>
</template>


<script>
import posts from "@/dades/posts.js"
export default{
    mounted(){
       console.log(posts)
       this.postsDeVue = posts
    },
    data(){
        return{
            postsDeVue:[]
        }
    },
    methods:{
        enllacIdArticle(){

        }
    }
}
</script>