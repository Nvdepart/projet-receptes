<template>
  <v-container>
    <v-row>
      <v-col cols="12">
        <h1 style="font-size: 10vw">COKTAIL<span style="font-weight: 100;font-style: italic">TIME</span></h1>
        <v-row>
          <v-col cols="3" v-for="recepta in receptes" :key="recepta.idDrink">
            <v-img :src="recepta.strDrinkThumb">
              <v-container style="height: 100%" fill-height>
                <v-row style="height: 100%" >
                  <v-col align="end" justify="end">
                    <h3>{{recepta.strDrink}}</h3>
                  </v-col>
                </v-row>
              </v-container>
            </v-img>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import {receptes} from '@/dades/receptes'
export default{
  mounted(){
    console.log(receptes)
    this.receptes = receptes
    // Utilitzem les dades del plugin receptes
    //console.log(this.$receptes)
  },
  data(){
    return {
      receptes:[]
    }
  }
}
</script>
