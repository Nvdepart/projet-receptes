<template>
    <div>
       
        
        {{textEsquerre}}
      
        <a v-if="tipus=='url'" :href="url">{{textDreta}}</a>
        <span v-else>{{url}}</span>
        
    </div>
</template>
<script>
export default{
props:["tipus","textEsquerre","textDreta","url"]

}

</script>