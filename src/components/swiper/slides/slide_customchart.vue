<template>
    <div class="container-fluid content pt-3">
        <div class="row">
            {{ userId }} {{ jsonData }}
            <div v-for="user in users" v-bind:key="user.id">
                {{ user.address.suite }}
            </div>
        </div>
    </div>
</template>

<script>
import "vue3-circle-progress/dist/circle-progress.css";
// import CircleProgress from "vue3-circle-progress";
// import CustomChart from '@/components/Chart/CustomChart.vue';
// import jsonSup from '@/assets/variable_mapping/jsonstring.json'
import axios from 'axios';

export default {
    name: 'App',
    components: {
        // CircleProgress,
        // CustomChart,
    },
    data() {
        return {
            userId: '',
            users: [],
            jsonData: '',

        }
    },

    created() {
        axios.get('https://jsonplaceholder.typicode.com/users')
            .then(response => {
                this.users = response.data
            });
        // this.jsonData = require("@/assets/variable_mapping/jsonstring.json");
        // this.jsonData = jsonSup;
        // const jsonSet = {
        //     "Home": {
        //         "Number": 666,
        //         "People": 600
        //     }
        // }
        // this.jsonData = jsonSet;
    }
}
</script>

<style>

</style>