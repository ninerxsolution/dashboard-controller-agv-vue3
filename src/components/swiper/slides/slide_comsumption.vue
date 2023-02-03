<template>
    <div class="container-fluid content bg-dark pt-3">
        <div class="row">
            <div class="col-md-4 grid-margin stretch-card">
                <CardConsumpTotal />
            </div>
            <div class="col-md-8 grid-margin stretch-card">
                <CardTrendTotal :msg="jsonData"/>
            </div>
        </div>

        <div class="row">
            <div class="col-md-4 grid-margin">
                <CardAgvRunning />
                <CardDataTrack />
            </div>
            <div class="col-md-4 grid-margin">
                <CardSelectAgv />
                <CardLogoAgv />
                <CardBatteryCap />
            </div>
            <div class="col-md-4 grid-margin">
                <CardElecVol />
                <CardElecCurrMon />
            </div>

            Loop test api : <div v-for="loop of jsonData" :key="loop.id">{{ loop.time }}</div>
            Json test here! : {{ jsonData }}
            <br>
            
        </div>
    </div>
</template>

<script>
import CardConsumpTotal from './slide_consumption/card_consumption_total.vue';
import CardTrendTotal from './slide_consumption/card_trend_yield_energy_total.vue';
import CardAgvRunning from './slide_consumption/card_agv_running_now.vue';
import CardDataTrack from './slide_consumption/card_data_track.vue';
import CardSelectAgv from './slide_consumption/card_select_agv.vue';
import CardLogoAgv from './slide_consumption/card_logo_agv.vue';
import CardBatteryCap from './slide_consumption/card_battery_capacity.vue';
import CardElecVol from './slide_consumption/card_electrical_voltage_agv.vue';
import CardElecCurrMon from './slide_consumption/card_electrical_current_for_monitor.vue';
// import { response } from 'express';
// import axios from 'axios';

export default {
    name: 'App',
    components: {
        CardConsumpTotal,
        CardTrendTotal,
        CardAgvRunning,
        CardDataTrack,
        CardSelectAgv,
        CardLogoAgv,
        CardBatteryCap,
        CardElecVol,
        CardElecCurrMon,
    },
    props: {
        getJson: {
            type: Object,
        }
    },
    data() {
        return {
            jsonData: null,
            thrower: 'Annalists',
            data_lists: [10000,2,3,5,4,3,2,4,5,4,3,2],
        }
    },
    // created() {
    //     this.fetchData();
    //     setInterval(() => {
    //         this.fetchData()
    //     },1000)
    // },
    // computed: {

    // },
    // methods: {
    //     async fetchData() {
    //         try {
    //             const response = await axios.get('https://se-sskru.com/ev-rail/json/AGV_1/-1')
    //             this.jsonData = response.data.graph.monthly
    //         } catch (error) {
    //             console.error(error)
    //         }
    //     }
    // }
}
</script>

<style>
.progress {
    width: 70%
}

@media (min-width: 1000px) {
    .progress {}
}

@media (min-width: 1100px) {
    .progress {}
}

@media (min-width: 1300px) {
    .progress {}
}

@media (min-width: 1406px) {
    .progress {
        width: 70%;
        color: #ffd000;
    }
}
</style>