<template>
    <v-container fluid class='homepage ma-0 pa-0' app >
        <navigation id="nav"></navigation>
            <banner/>
            <tools/>
            <about/>
            <portfolio></portfolio>
            <contact/>
            <myFooter></myFooter>
    </v-container>
</template>

<script>
import navigation from "./navigation.vue"
import banner from "./banner.vue"
import tools from "./tools.vue"
import about from "./about.vue"
import portfolio from "./portfolio.vue"
import contact from "./contact.vue"
import myFooter from "./footer.vue"
export default {
    name:'homepage',
    components:{
        navigation,banner,tools,about,portfolio,contact,myFooter
    }
}
</script>

<style scoped >
#nav{
    position: fixed;
    z-index: 4;
}


</style>