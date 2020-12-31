<template>
    <v-card>
        <v-card-title>
            ASW Overview
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
                        <td class="hull">{{ item.hull }}</td>
                        <td class="date">{{ item.date }}</td>
                        <td class="report-name" :class="item.uploadDateClass">{{ item.name }}</td>
                        <td class="ext">{{ item.ext }}</td>
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
        name: "asw-table",
        data() {
            return {

                search: '',
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
        //props: {
        //    reports: {
        //        type: Array,
        //        required: true,
        //        default:
        //            function () {
        //                return [];
        //            }
        //    }
        //},
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
            row_onclick: function (e) {
                console.log(e, " was clicked");
            }
        },
        computed: {
            root: function () {
                return null;//document.getElementById('App-base-url').value;
            },
            headers: function () {
                return [{
                    text: "Status",
                    value: "status",
                    "class": "status"
                }, {
                    text: "Hull",
                    value: "hull",
                    "class": "hull"
                }, {
                    text: "Ship",
                    value: "ship",
                    "class": "ship"
                }, {
                    text: "Months",
                    value: "months",
                    "class": "months"
                }, {
                    text: "Date",
                    value: "reportDate",
                    "class": "report-date"
                }, {
                    text: "Report name",
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
            return [];
        }
    })

</script>
<style scoped>
</style>