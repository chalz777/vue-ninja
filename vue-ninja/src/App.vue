<template>
  
    <v-app>
        <v-system-bar app class="text-center" color="red" dark>
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

           
            <v-app-bar app>
                <h2>Surface Ship Radiated Noise Measurement</h2>
                <v-spacer></v-spacer>
                <v-toolbar-items class="hidden-sm-and-down">
                    <v-btn>
                        <v-icon>mdi-antenna</v-icon>
                        <router-link to="/">Atlantic Fleet</router-link>
                    </v-btn>
                    <v-btn>
                        <v-icon>mdi-history</v-icon>
                        <router-link to="/ssrnm">SSRNM Main</router-link>
                    </v-btn>
                    <v-btn>
                        <v-icon>mdi-plus</v-icon>
                        <router-link to="/about">About</router-link>
                    </v-btn>
                </v-toolbar-items>


            </v-app-bar>
            <v-main>
                <v-container fluid>
                    <router-view :parentComponent="currItem" />
                </v-container>
            </v-main>
            <v-footer app>
                <!-- -->
            </v-footer>

</v-app>
</template>

<script lang="ts">
    /* eslint-disable vue/no-unused-components */
    import Vue from 'vue';
    import SsrnmMain from '@/views/SsrnmMain.vue'; 

export default Vue.extend({

  name: 'App',

  components: {
      SsrnmMain
    },
    data: () => ({
        navItems: [{
            id: 0,
            link: "landing-page",
            title: "SSRNM Main"
            , header: "ATLANTIC FLEET"
        }, {
            id: 1,
            link: "",
            title: "ATLANTIC FLEET"
            , header: "ATLANTIC FLEET"
        }, {
            id: 2,
            link: "trials-table",
            title: " - TRIAL HISTORY"
            , header: "ATLANTIC FLEET"
        }
        ],
        currItem: '',
    }),
    methods: {
        navItem_onclick(item) {
            this.currItem = item
        },
    }
});
</script>
