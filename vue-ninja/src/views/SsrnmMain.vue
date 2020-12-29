<template>
    <v-container>
        <v-row class="text-center" style="height: 200px;">
            <v-col cols="12" >
                <v-spacer />
            </v-col>
        </v-row>

        <v-row class="text-center">
            <v-col cols="12" class="pa-md-1 my-lg-auto" color="white">
                <component v-bind:is="component" />
                <button v-on:click="toggle">Toggle</button>
                <!--<TrailsTable2 msg="Welcome to Your Vue.js + TypeScript App" />
    <component :is="currentMainComponent" v-bind="currentMainProperties" v-on="currentMainEvents"> </component>-->
            </v-col>
        </v-row>
    </v-container>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
    import TrailsTable from '@/components/TrailsTable.vue'; // @ is an alias to /src
    import TrailsTable2 from '@/components/TrailsTable2.vue'; // @ is an alias to /src

@Component({
    components: {
        TrailsTable,
        TrailsTable2
    },
    data: function () {
        return {
            component: "TrailsTable",
            header: "",
            isNoticeRendered: false,
            currentMainComponent: "landing-page",
        }
    },
    methods: {
        toggle() {
            if ((this as any).component === TrailsTable) {
                (this as any).component = TrailsTable2;
            } else {
                (this as any).component = TrailsTable;
            }
        }
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
