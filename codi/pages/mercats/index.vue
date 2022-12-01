<template>
    <v-container>
        <v-row>
            <v-col cols="12">
                <h1 style="font-size: 10vw">Mercats<span style="font-weight: 100%;font-style: italic">Barcelona</span></h1>
                <v-row>
                    <v-col cols="3" v-for="mercat in mercats" :key="mercat.register_id">
                        <v-img :src="mercat.image_data.image" style="height:20vh">
                            <v-container style="height: 100%" fill-height>
                                <v-row style="height: 100%" align="end" justify="end" >
                                  <v-col align="end">
                                    <h3>{{mercat.name}}</h3>
                                    <h4>{{mercat.status_name}}</h4>
                                    <nuxt-link :to="'/mercat/'+mercat.register_id">Veure mercat</nuxt-link>
                                  </v-col>
                                </v-row>
                              </v-container>
                            </v-img>
                    </v-col>
                </v-row>
            </v-col>
            <v-col cols="12">
                <pre> Barcelona té {{numeros}} mercats</pre>
            </v-col>
        </v-row>
    </v-container>
</template>
<script>
//import * as everything from '@/dades/mercats.js'
import {llistaMercats,numeroDeMercats} from '@/dades/mercats.js'
export default{
            mounted(){
                    this.mercats = llistaMercats
                    this.numeros = numeroDeMercats
            },
            data(){
                return {
                    mercats:[],
                    numeros:""
                }
            },
            watch:{
            mercatVue(){
                console.log("Ha canviat",this.mercatVue)
                }
            }
}


</script>