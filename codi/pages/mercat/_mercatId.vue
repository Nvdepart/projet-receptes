<template>
    <v-container>
        <v-row>
            <v-col cols="12" md="6">
                <h1>{{mercatVue.name}}</h1>
                <v-img :src="mercatVue.image_data.image" style="height:20vh"></v-img>
            </v-col>
            <div>
                <enllaç v-for="web in mercatVue.values"
                :textEsquerre="web.attribute_name"
                :textDreta="web.url_visible_value"
                :url="web.value"
                :tipus="web.attribute_type"
                ></enllaç>
            </div>
            <v-col cols="12" md="6">
               <a 
               v-if="mercatVue"
               target="_blank"
               :href="mercatVue.values[0].url_value"
               >
                {{mercatVue.values[0].url_visible_value}}
               </a>
            </v-col>
        </v-row>

    </v-container>
</template>

<script>
import {buscarMercat} from '@/dades/mercats.js'

export default {

        created(){
            let mercat = 
            buscarMercat(this.$route.params.mercatId)
            this.mercatVue = mercat
        },
    data(){
            return {
                mercatVue:{}
            }
        }

}

</script>