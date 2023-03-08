<template>
    <v-container fluid class='homepage ma-0 pa-0' app >
        <navigation id="nav"></navigation>
            <banner/>
    </v-container>
</template>

<script>
import navigation from "./navigation.vue"
import banner from "./banner.vue"
export default {
    name:'homepage',
    components:{
        navigation,banner
    }
}
</script>

<style scoped >
#nav{
    position: fixed;
    z-index: 4;
}


</style>