<template>
    <!--<v-card height="400"
            width="256"
            class="mx-auto">
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
    </v-card>-->
    
    

       
        <!--<v-row class="text-center" style="height: 200px;">
        <v-col cols="12">
            <v-spacer />
        </v-col>
    </v-row>-->



        <v-row class="text-center">
            <v-col cols="12" class="pa-md-1 my-lg-auto" color="white">
                <component v-bind:is="component" />
                
                <v-card>{{parentComponent.link}}</v-card>
               
                <!--<TrailsTable2 msg="Welcome to Your Vue.js + TypeScript App" />-->
                <!--<component :is="currentMainComponent" v-bind="currentMainProperties" v-on="currentMainEvents"> </component>-->
            </v-col>
        </v-row>

</template>

<script lang="ts">
    import { Component, Vue } from 'vue-property-decorator';
    import LandingPage from '@/components/LandingPage.vue'; 
    import TrailsTable from '@/components/TrailsTable.vue'; // @ is an alias to /src
    import TrailsTable2 from '@/components/TrailsTable2.vue'; 
    import AswTable from '@/components/AswTable.vue'; 

    @Component({
        components: {
            LandingPage,
            TrailsTable,
            TrailsTable2,
            AswTable,
        },
        props: ['parentComponent'],       
        data: function () {
            return {
                component: LandingPage,
                header: "",
                isNoticeRendered: false,
                currentMainComponent: "landing-page",
                parentComp: (this as any).parentComponent,
            }
        },
    methods: {
        changeComp(link) {
            //alert("parentmessage has changed: " + link);
            //if ((this as any).component === TrailsTable) {
            if (link == "landing-page") {
                (this as any).component = LandingPage;
            } else if (link == "trials-table") {
                (this as any).component = TrailsTable2;
            } else if (link == "asw-table") {
                (this as any).component = AswTable;
            } else {
                (this as any).component = LandingPage;
            }
            
        },
    },
    watch: {
        parentComponent: function () {
            //alert("parentmessage has changed: " + (this as any).parentComponent.title);
            (this as any).changeComp((this as any).parentComponent.link);            
        },
    },
    computed: {
        currentMainProperties: function () {
            return {};
        },
        currentMainEvents: function () {
            return {};
        }
    },
})
export default class Home extends Vue {}
</script>
