<template>
    <div>
        <v-alert :color="type" icon="mdi-alert-circle-check"  v-if="type">
            This is a success alert.
        </v-alert>
        <v-btn color="light" @click="showAlert('info')">info</v-btn>
        <v-btn color="light" @click="showAlert('success')">success</v-btn>
        <v-btn color="light" @click="showAlert('warning')">warning</v-btn>
        <v-btn color="light" @click="showAlert('error')">error</v-btn>
        <v-btn color="light">{{elapse}}</v-btn>
    </div>


</template>

<script lang="ts">
    import Vue from 'vue'   
    export default Vue.extend({
        name: "asw-table",
        data() {
            return {                
                elapse: 0,
                alertType: null,
            }
        },
        props: {
            type: {
                type: String,                
            },
        },
        methods: {
            showAlert(inType) {
                this.alertType = inType

                const timer = (this as any).showAlert.timer
                if (timer) {
                    clearTimeout(timer)
                }
                (this as any).showAlert.timer =
                    setTimeout(() => {
                        this.alertType = null
                    }
                        , 3000)

                this.elapse = 1;
                const t = this.showAlert.t
                if (t) {
                    clearInterval(t)
                }

                this.showAlert.t = setInterval(() => {
                    if (this.elapse === 3) {
                        this.elapse = 0
                        clearInterval(this.showAlert.t)
                    }
                    else {
                        this.elapse++
                    }
                }, 1000)
            },
        },
    
    })

</script>
<style scoped>
</style>