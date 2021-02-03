<template>
    <nav>
        <v-app-bar flat app>
            <v-app-bar-nav-icon class="grey--text" @click="drawer = !drawer"></v-app-bar-nav-icon>
            <v-toolbar-title class="text-uppercase grey--text">
                <span class="font-weight-light">Danya</span>
                <span>Danya</span>
            </v-toolbar-title>
        </v-app-bar>

        <v-navigation-drawer app v-model="drawer" temporary class="deep-purple--text text--accent-4">
            <v-layout column align-center>
            </v-layout>
            <v-list>
                <v-list-item v-for="link in links" :key="link.text" router :to="link.route">
                    <v-list-item-action>
                        <v-icon left class="black--text" id="amr">{{ link.icon }}</v-icon>
                    </v-list-item-action>
                    <v-list-item-content>
                        <v-list-item-title class="black--text" id="amr">{{ link.text }}</v-list-item-title>
                    </v-list-item-content><br>
                </v-list-item>
            </v-list>
        </v-navigation-drawer>
    </nav>
</template>

<script>
import { mdiVideoVintage, mdiAirplane   } from '@mdi/js';
export default {
    data() {
        return {
            icons: {
                mdiVideoVintage,
                mdiAirplane  
            },
            drawer: false,
            links: [
                { icon: 'mdi-home', text: 'Home', route: '/' },
                { icon: 'mdi-video-vintage', text: 'Videos', route: '/videos' },
            ]
        }
    },
}   
</script>

<style scoped>
    #amr {
        margin: 10px
    }
</style>