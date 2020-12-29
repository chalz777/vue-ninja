<template>
  
    <v-app>
        <!--<v-navigation-drawer app>
            nnknknk
        </v-navigation-drawer>-->
        <v-navigation-drawer app dark>
            <v-list nav>
                <v-list-item link v-for="item in navItems" :key="item.id" @click="navItem_onclick(item)">
                    <v-list-item-content>
                        <v-list-item-title>
                            {{item.title}}
                        </v-list-item-title>
                    </v-list-item-content>
                </v-list-item>
            </v-list>
        </v-navigation-drawer>

        <!--<v-col class="mb-5 error" cols="12">
    This site contains dynamic content - Highest Possible Classification is SECRET
    </v-col>-->
        <v-app-bar app>


            <v-toolbar-title class="headline text-uppercase">
                <v-system-bar class="text-center" color="red " dark>
                    <v-row class="text-center">
                        <v-spacer />
                        <span class="black--text">
                            This site contains dynamic content - Highest Possible Classification is SECRET
                        </span>
                    </v-row>
                    <v-spacer></v-spacer>
                    <v-icon>mdi-wifi-strength-4</v-icon>
                    <v-icon>mdi-signal-cellular-outline</v-icon>
                    <v-icon>mdi-battery</v-icon>
                    <span>12:30</span>
                </v-system-bar>
                <span>Surface Ship Radiated Noise Measurement</span>
            </v-toolbar-title>
            <v-spacer></v-spacer>
            <v-toolbar-items class="hidden-sm-and-down">
                <v-btn>
                    <v-icon>mdi-history</v-icon>
                    <router-link to="/">Atlantic Fleet</router-link>
                </v-btn>
                <v-btn>
                    <v-icon>mdi-history</v-icon>
                    <router-link to="/ssrnm">SSRNM Main</router-link>
                </v-btn>
                <v-btn>
                    <v-icon>mdi-history</v-icon>
                    <router-link to="/about">About</router-link>
                </v-btn>
            </v-toolbar-items>


        </v-app-bar>
        <v-main>
            <v-container fluid>
                <router-view />
            </v-container>
        </v-main>
        <v-footer app>
            <!-- -->
        </v-footer>

    </v-app>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'App',

  components: {
    
    },
    data: () => ({
    }),
});
</script>
