<template>
    <v-container fluid class='homepage ma-0 pa-0' app >
        <navigation id="nav"></navigation>
            <banner/>
            <tools/>
    </v-container>
</template>

<script>
import navigation from "./navigation.vue"
import banner from "./banner.vue"
import tools from "./tools.vue"
export default {
    name:'homepage',
    components:{
        navigation,banner,tools
    }
}
</script>

<style scoped >
#nav{
    position: fixed;
    z-index: 4;
}


</style>