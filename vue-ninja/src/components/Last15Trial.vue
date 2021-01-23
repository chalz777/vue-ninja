<template>

    <v-card>
        <v-card-title>
            Non ASW Overview
            <v-spacer />
            <v-text-field v-model="search"
                          label="Search"
                          class="list-search"
                          single-line
                          hide-details />
        </v-card-title>

        <v-data-table :headers="headers"
                      :items="itemsDisplay"
                      :search="search"
                      item-key="id"
                      class="route-list-table">

            <template v-slot:body="{ items }">
                <tbody>
                    <tr class="pointer" :class="item.rowClass" v-for="item in items" :key="item.id">
                        <td class="ship">{{ item.ship }}</td>
                        <td class="years">{{ item.years }}</td>
                        <td class="date">{{ item.date }}</td>
                        <td class="message">{{ item.message }}</td>
                        <td class="report-name" :class="item.uploadDateClass">{{ item.name }}</td>
                    </tr>
                </tbody>
            </template>
        </v-data-table>
    </v-card>

</template>

<script lang="ts">

    import Vue from 'vue'
    import * as DataAccess from '../assets/js/dataAccess'
    export default Vue.extend({
        name: "search-form",
        components: {         
        },
        data() {
            return {
                search: '',
                yourDateString: '2018-12-24 04:19:23',
                slots: [
                    'body',
                    'body.append',
                    'body.prepend',
                    'footer',
                    'header.data-table-select',
                    'header',
                    'header.<name>',
                    'progress',
                    'item.data-table-select',
                    'item.<name>',
                    'no-data',
                    'no-results',
                    'top'
                ],
                items: [],
               
            }
        },
        methods: {
            /* 		deleteItem: function (item) {
            console.log("deleteItem", item);
            var self = this;
            DataAccess.deleteAttachment(item.id)
            .then(function (data) {
            console.log("data", data);
            self.files.splice(self.files.findIndex(x => x.id === item.id), 1);
            //self.$toasted.success("Record " + id + " removed");
            })
            .catch(function (err) {
            console.log(err);
            //self.$toasted.error("Failed to remove record " + id);
            });
            },
             */
            getReports: function () {
                return [
                    {
                        id: 1
                        , hull: "hull1"
                        , status: "status1"
                        , ship: "ship1"
                        , months: "months1"
                        , reportDate: this.dateFormat(new Date(0))
                        , reportName: "name1"
                    },
                    {
                        id: 2
                        , hull: "hull2"
                        , status: "status2"
                        , ship: "ship2"
                        , months: "months2"
                        , reportDate: this.dateFormat(new Date(0))
                        , reportName: "name2"
                    },
                    {
                        id: 3
                        , hull: "hull3"
                        , status: "status3"
                        , ship: "ship3"
                        , months: "months3"
                        , reportDate: this.dateFormat(new Date(0))
                        , reportName: "name3"
                    },
                    {
                        id: 4
                        , hull: "hull4"
                        , status: "status4"
                        , ship: "ship4"
                        , months: "months4"
                        , reportDate: this.dateFormat(new Date(0))
                        , reportName: "name4"
                    },
                    {
                        id: 5
                        , hull: "hull5"
                        , status: "status5"
                        , ship: "ship5"
                        , months: "months5"
                        , reportDate: this.dateFormat(new Date(0))
                        , reportName: "name5"
                    }
                ];
            },
            dateFormat: function (e) {
                return new Intl.DateTimeFormat('en-US', {
                    year: 'numeric',
                    month: 'numeric',
                    day: 'numeric',
                    hour: 'numeric',
                    minute: 'numeric',
                    second: 'numeric',
                }).format(e);
            },

            row_onClick: function (e) {
                console.log(e, " was clicked");
                (this as any).$vToastify.info("body", "title");
            }
        },
        computed: {
            root: function () {
                return null;//document.getElementById('App-base-url').value;
            },
            headers: function () {
                return [{
                    text: "ship",
                    value: "ship"
                }, {
                    text: "years",
                    value: "years",
                    "class": "years"
                }, {
                    text: "date",
                    value: "reportDate",
                    "class": "report-date"
                }, {
                    text: "Message",
                    value: "message",
                    "class": "message"
                }, {
                    text: "report name",
                    value: "reportName",
                    "class": "report-name",
                    sort: function (a, b) {
                        return a - b;
                    }
                },
                ];
            },
            itemsDisplay: function () {
                const self = (this as any);
                if (self.items.sort) {
                    return self.items.sort((a: any, b: any) => {
                        return a - b;
                    });
                } else {
                    return [];
                }
            }
        },
        mounted: function () {
            (this as any).items = this.getReports();
        }

    })

</script>
<style scoped>
</style>