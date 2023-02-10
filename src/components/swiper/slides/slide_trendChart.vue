<template>
    <div class="container-fluid content  pt-3">
        <div class="row">
            <div class="col-md-3 grid-margin stretch-card">
                <CardDefExportTotal :v-bind="ChartChoose"/>
            </div>
            <div class="col-md-9 grid-margin stretch-card">
                <CardTrendTotal :barchartData="allChart" :v-model="ChartChoose"/>
                <!-- <span>{{ trendEnergy }}</span> -->
            </div>
        </div>

        <div class="row">
            <div class="col-12 grid-margin">
                <CardTrendSelectAgv :powerChart="powerChart" :currentChart="currentChart" :speedchart="speedchart"/>
            </div>
        </div>
        <!-- <span>{{ powerChart }}</span>
        <span>{{ speedchart }}</span>
        <span>{{ currentChart }}</span> -->
    </div>
</template>

<script>
import "vue3-circle-progress/dist/circle-progress.css";
import CardDefExportTotal from './slide_trend_chart/card_default_export_total.vue';
import CardTrendTotal from './slide_trend_chart/card_trend_energy_agv_total.vue';
import CardTrendSelectAgv from './slide_trend_chart/card_trend_select_agv.vue';

export default {
    name: 'App',
    components: {
        CardDefExportTotal,
        CardTrendTotal,
        CardTrendSelectAgv,
    },
    props:{
        getJson:{
            type:Object
        },
    },
    data() {
        return {
            powerChart:'',
            speedchart:'',
            currentChart:'',
            allChart:'',
            detail_export: [
                { name: 'ENERGY AGV TOTAL', check: true },
                { name: 'PRODUCTION TOTAL', check: true },
                { name: 'CYCLE TRANSPORT', check: false },
                { name: 'POWER AGV TOTAL', check: true },
                { name: 'TEST', check: false },
                { name: 'TEST', check: false },
                { name: 'TEST', check: true },
                { name: 'TEST', check: false },
                { name: 'TEST', check: false },
            ],
            trend_select_agv: [
                { name: 'SPEED AGV 1', check: true },
                { name: 'SPEED AGV 2', check: false },
                { name: 'SPEED AGV 3', check: false },
                { name: 'POWER AGV 1', check: true },
                { name: 'POWER AGV 2', check: false },
                { name: 'POWER AGV 3', check: false },
                { name: 'CURR AGV 1', check: true },
                { name: 'CURR AGV 2', check: false },
                { name: 'CURR AGV 3', check: false },

            ]
        }
    },
    created(){
        setInterval(()=>{
            this.allChart = this.getJson.graph
            this.powerChart = this.getJson.return.data.pages.page4.TREND_SELECT.power_trend.value
            this.speedchart = this.getJson.return.data.pages.page4.TREND_SELECT.speed_trend.value
            this.currentChart = this.getJson.return.data.pages.page4.TREND_SELECT.current_trend.value
        },1000)
    }
}
</script>

<style>
@media (min-width: 1000px) {}

@media (min-width: 1100px) {}

@media (min-width: 1300px) {}

@media (min-width: 1406px) {}

.dummy-meter {
    margin: auto;
    /* color: #00a2ff; */
}

/* scrollbar */
.scrollbar{
    /* margin-left: 30px; */
    /* float: left; */
    /* height: 8rem; */
    /* width: 65px; */
    /* background: #fff; */
    overflow-y: scroll;
    /* margin-bottom: 25px; */
}


.scrollbar::-webkit-scrollbar {
    width: 10px;
    background-color: #000000;
}

.scrollbar::-webkit-scrollbar-thumb {
    border-radius: 20px;
    -webkit-box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.1);
    background-color: #ffffff;
}
</style>