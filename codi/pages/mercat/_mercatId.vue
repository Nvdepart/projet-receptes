<template>
    <v-container>
        <v-row>
            <v-col cols="12" md="6">
                <h1>{{mercat.mercatId}}</h1>
            </v-col>
            <v-col cols="12" md="6">
                <pre>
                    {{mercat}}
                </pre>
            </v-col>
        </v-row>

    </v-container>
</template>

<script>
import {llistaMercats} from '@/dades/mercats.js'

export default {
        mounted(){
            let mercatId = this.$route.params.register_id
            llistaMercats.forEach(element => {
                if(mercatId==element.mercatId){
                // Hem trobat la recepta
                // self.recepta = recepta
                this.mercat = element
            }
            });

        },
    data(){
            return {
                mercat:[]
            }
        }

}

</script>