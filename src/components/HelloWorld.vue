<template>
    <v-container>

        <v-row class="text-center">
            <v-col cols="12">
                <v-img :src="require('../assets/logo.svg')"
                       class="my-3"
                       contain
                       height="200" />
            </v-col>
        </v-row>
        <v-row class="text-center">
            <v-col class="mb-5" cols="12">
                <v-main app dark>
                    <v-container dark>
                        <h2>ASW Range Program Manager - Mr Neal Prater</h2>
                        <hr />
                        <h2>NAVAL SEA SYSTEMS COMMAND - SEA 05H3</h2>
                        <v-card>
                            <!--<v-card-title>{{header}}</v-card-title>
                            <component :is="currentMainComponent" v-bind="currentMainProperties" v-on="currentMainEvents"> </component>-->
                        </v-card>
                    </v-container>
                </v-main>
            </v-col>
        </v-row>
        <v-container class="grey lighten-5">
            <v-row no-gutters>
                <v-col ></v-col>
                <v-col v-for="n in 3"
                       :key="n"
                       cols="12"
                       sm="4">
                    <v-card class="pa-2"
                            outlined
                            tile>
                        One of three columns
                    </v-card>
                </v-col>
            </v-row>
        </v-container>



        <!--<v-dialog class="front" v-model="isNoticeRendered" :key="isNoticeRendered" transition="slide-x-transition">
    <dod-notice @click="isNoticeRendered = false" class="front"> </dod-notice>
    </v-dialog>-->
        <!--<v-navigation-drawer app dark>
        <v-list nav>
            <v-list-item link v-for="item in navItems" :key="item.id" @click="navItem_onclick(item)">
                <v-list-item-content>
                    <v-list-item-title>
                        {{item.title}}
                    </v-list-item-title>
                </v-list-item-content>
            </v-list-item>
        </v-list>
    </v-navigation-drawer>-->

        <v-expansion-panels>
            <v-expansion-panel v-for="(item,i) in 5"
                               :key="i">
                
                <v-expansion-panel-header>
                    Item
                </v-expansion-panel-header>
                <v-expansion-panel-content>
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                </v-expansion-panel-content>
            </v-expansion-panel>
        </v-expansion-panels>


    </v-container>
</template>

<script lang="ts">
  import Vue from 'vue'

  export default Vue.extend({
    name: 'HelloWorld',

    data: () => ({
      ecosystem: [
        {
          text: 'vuetify-loader',
          href: 'https://github.com/vuetifyjs/vuetify-loader',
        },
        {
          text: 'github',
          href: 'https://github.com/vuetifyjs/vuetify',
        },
        {
          text: 'awesome-vuetify',
          href: 'https://github.com/vuetifyjs/awesome-vuetify',
        },
      ],
      importantLinks: [
        {
          text: 'Documentation',
          href: 'https://vuetifyjs.com',
        },
        {
          text: 'Chat',
          href: 'https://community.vuetifyjs.com',
        },
        {
          text: 'Made with Vuetify',
          href: 'https://madewithvuejs.com/vuetify',
        },
        {
          text: 'Twitter',
          href: 'https://twitter.com/vuetifyjs',
        },
        {
          text: 'Articles',
          href: 'https://medium.com/vuetify',
        },
      ],
      whatsNext: [
        {
          text: 'Explore components',
          href: 'https://vuetifyjs.com/components/api-explorer',
        },
        {
          text: 'Select a layout',
          href: 'https://vuetifyjs.com/getting-started/pre-made-layouts',
        },
        {
          text: 'Frequently Asked Questions',
          href: 'https://vuetifyjs.com/getting-started/frequently-asked-questions',
        },
      ],
    }),
  })
</script>
