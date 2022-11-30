<template>
    <v-container>
        <v-row>
            <v-col cols="12" md="6">
                <h1>{{receptaVue.strDrink}}</h1>
            </v-col>
            <v-col cols="12" md="6">
                <pre>
                    {{receptaVue}}
                </pre>
            </v-col>
        </v-row>

    </v-container>
</template>

<script>
import {receptes} from '@/dades/receptes.js'

export default{

    mounted(){
        let idDrink = this.$route.params.idDrink
        // Buscar la recepta 
        // var self = this
        receptes.forEach(recepta => {
            if(idDrink==recepta.idDrink){
                // Hem trobat la recepta
                // self.recepta = recepta
                this.receptaVue = recepta
            }
        });
    },
    
    data(){
        return{
            receptaVue:{}
        }
    }
}

</script>