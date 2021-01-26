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
                                
                                    <v-icon v-text="item.icon" :size="item.isize"></v-icon>
                              
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
                        <v-icon>mdi-home</v-icon>
                        <router-link to="/ssrnm">SSRNM Main</router-link>
                    </v-btn>
                    <v-btn>
                        <v-icon>mdi-ship-wheel</v-icon>
                        <router-link to="/">Atlantic Fleet</router-link>
                    </v-btn>
                    <v-btn>
                        <v-icon>mdi-head-question</v-icon>
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
      SsrnmMain,     
    },
    data: () => ({
        navItems: [{
            id: 0,
            link: "landing-page",
            icon: "mdi-home",
            isize: "22",
            title: "SSRNM Main"
            , header: "ATLANTIC FLEET"
        }, {
            id: 1,
                link: "",
                icon: "mdi-ship-wheel",
                isize: "22",
            title: "ATLANTIC FLEET"
            , header: "ATLANTIC FLEET"
        }, {
            id: 2,
                link: "trials-table",
                icon: "mdi-sail-boat",
                isize: "19",
            title: " - TRIAL HISTORY"
            , header: "ATLANTIC FLEET"
        }, {
                id: 3,
                link: "asw-table",
                icon: "mdi-google-analytics",
                isize: "19",
                title: " - ASW OVERVIEW"
                , header: "ATLANTIC FLEET"
        },{
                id: 4,
                link: "non-asw-table",
                icon: "mdi-google-circles-extended",
                isize: "19",
                title: " - NON ASW OVERVIEW"
                , header: "NON ATLANTIC FLEET"
            
        }, {
                id: 5,
                link: "search-form",
                icon: "mdi-google-circles",
                isize: "19",
                title: " - SEARCH"
                , header: "SEARCH"
        }, {
                id: 6,
                link: "reports-list",
                icon: "mdi-view-headline",
                isize: "19",
                title: " - REPORTS LIST"
                , header: "REPORTS LIST"
        }, {
                id: 7,
                link: "last-15-trials",
                icon: "mdi-google-lens",
                isize: "19",
                title: " - LAST 15 TRIALS"
                , header: "LAST 15 TRIALS"
        }, {
                id: 8,
                link: "contacts",
                icon: "mdi-arrow-up-bold-hexagon-outline",
                isize: "19",
                title: " - CONTACTS"
                , header: "CONTACTS"
        }, {
                id: 9,
                link: "coming-soon",
                icon: "mdi-google-play",
                isize: "19",
                title: " - COMING SOON"
                , header: "COMING SOON"
        }, {
                id: 10,
                link: "dod-notice",
                icon: "mdi-google-hangouts",
                isize: "19",
                title: " - DOD NOTICE"
                , header: "DOD NOTICE"
        },
            //{
        //        id: 5,
        //        link: "reuse-tabs",
        //        icon: "mdi-airplane",
        //        isize: "22",
        //        title: " - reuse-tabs"
        //        , header: "reuse-tabs FLEET"
        // },
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
