<template>
          <v-container>
            <v-row>
              <v-col>
                <h1>Home</h1>
                <nuxt-link to="/receptes"></nuxt-link> 
              </v-col>
            </v-row>
          </v-container>
</template>
<script>
export default{
            mounted(){
              const axios = require("axios");

                    const options = {
                      method: 'GET',
                      url: 'https://the-cocktail-db.p.rapidapi.com/list.php',
                      params: {c: 'list'},
                      headers: {
                        'X-RapidAPI-Key': '8f3b633174msh296321d2dd558d0p18770fjsn41eb33976e62',
                        'X-RapidAPI-Host': 'the-cocktail-db.p.rapidapi.com'
                      }
                    };

                    axios.request(options).then(function (response) {
                      console.log(response.data);
                    }).catch(function (error) {
                      console.error(error);
                    });
            }

}


</script>