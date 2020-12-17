<template>
    <v-app>
        <!--<v-app-bar app
               color="primary"
               dark>
        <div class="d-flex align-center">
            <v-img alt="Vuetify Logo"
                   class="shrink mr-2"
                   contain
                   src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
                   transition="scale-transition"
                   width="40" />

            <v-img alt="Vuetify Name"
                   class="shrink mt-1 hidden-sm-and-down"
                   contain
                   min-width="100"
                   src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
                   width="100" />
        </div>

        <v-spacer></v-spacer>
        <v-btn href="https://github.com/vuetifyjs/vuetify/releases/latest"
               target="_blank"
               text>
            <span class="mr-2">Latest Release</span>
            <v-icon>mdi-open-in-new</v-icon>
        </v-btn>
    </v-app-bar>-->
        <v-system-bar class="text-center" color="red " dark>
            <v-row class="text-center">
                <v-spacer></v-spacer>
                <span class="black--text">
                This site contains dynamic content - Highest Possible Classification is SECRET</span>
            </v-row>
                <v-spacer></v-spacer>
                <v-icon>mdi-wifi-strength-4</v-icon>
                <v-icon>mdi-signal-cellular-outline</v-icon>
                <v-icon>mdi-battery</v-icon>
                <span>12:30</span>
        </v-system-bar>
        <v-toolbar app>

            <!--<v-col class="mb-5 error" cols="12">
            This site contains dynamic content - Highest Possible Classification is SECRET
            </v-col>-->
        

            <v-toolbar-title class="headline text-uppercase">
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
                    <router-link to="/home2">Pacific fleet</router-link>
                </v-btn>
                <v-btn>
                    <v-icon>mdi-history</v-icon>
                    <router-link to="/about">About</router-link>
                </v-btn>               
            </v-toolbar-items>
        </v-toolbar>

        <v-content>
            <router-view />
        </v-content>

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
