<template>
    <div class="container-fluid content bg-dark pt-3">
        <div class="row">
            <div class="col-md-3 grid-margin stretch-card">
                <div class="card">
                    <div class="card-body">
                        <h5>
                            DEFAULT EXPORT TOTAL
                        </h5>
                        <div class="row">
                            <div class="col-12">
                                <div class="scrollbar scrollbar-success mb-3 bg-dark" style="height:10rem;">
                                    <table class="table table-sm table-borderless mt-2">
                                        <tbody>
                                            <tr v-for="tsa in detail_export" :key="tsa">
                                                <td scope="row"
                                                    class="text-left text-warning d-flex justify-content-between">
                                                    <ul class="mb-2">
                                                        <li>
                                                            {{ tsa.name }}
                                                        </li>
                                                    </ul>
                                                    <div class="form-check p-0 m-0">
                                                        <input type="checkbox" class="form-check-input my-0"
                                                            :checked="tsa.check">
                                                    </div>
                                                </td>
                                            </tr>
                                        </tbody>
                                    </table>
                                </div>
                                <div class="col-12 d-flex justify-content-between p-0 m-0">
                                    <button class="btn btn-sm btn-warning text-dark">SELECT ALL</button>
                                    <button class="btn btn-sm btn-primary text-dark">EXPORT EXCEL</button>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-md-9 grid-margin stretch-card">
                <div class="card">
                    <div class="card-body">
                        <div class="col-12 d-flex justify-content-between">
                            <h5 class="d-flex">
                                TREND ENERGY AND AGV TOTAL
                            </h5>
                            <div class="text d-flex">
                                <div class="col-sm-6 h6 pt-1 text-right">SELECT TYPE:</div>
                                <div class="col-sm-6 text-warning pt-0">
                                    <div class="input-group-prependtop-left">
                                        <button class="btn btn-link dropdown-toggle text-warning pt-1" type="button"
                                            data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                                            ENERGY & YIELD
                                        </button>
                                        <div class="dropdown-menu">
                                            <a class="dropdown-item" href="#">Action</a>
                                            <a class="dropdown-item" href="#">Another action</a>
                                            <a class="dropdown-item" href="#">Something else here</a>
                                            <div role="separator" class="dropdown-divider"></div>
                                            <a class="dropdown-item" href="#">Separated link</a>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <BarChart />

                    </div>
                </div>
            </div>
        </div>
        <div class="row">

            <div class="col-12 grid-margin">
                <div class="card mb-4">
                    <div class="card-body">

                        <div class="col-12 d-flex justify-content-between px-0">
                            <div class="d-flex h5 mx-0 mt-1">
                                TREND SELECT AGV
                            </div>
                            <div class="d-flex">
                                <div class="input-group-prepend">
                                    <button class="btn btn-dark dropdown-toggle text-warning" type="button"
                                        data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                                        AGV1
                                    </button>
                                    <div class="dropdown-menu">
                                        <a class="dropdown-item" href="#">Action</a>
                                        <a class="dropdown-item" href="#">Another action</a>
                                        <a class="dropdown-item" href="#">Something else here</a>
                                        <div role="separator" class="dropdown-divider"></div>
                                        <a class="dropdown-item" href="#">Separated link</a>
                                    </div>
                                </div>
                            </div>
                            <div class="d-flex">
                                <button class="btn btn-dark mx-3">Date-time</button>
                                <span class="text-warning mx-0">STATUS: </span>
                                <span class="text-success mx-4">Online</span>
                            </div>
                        </div>

                        <div class="row">
                            <div class="col-9 mt-2">
                                <div class="row" style="height:;">
                                    <SpeedChart />
                                </div>
                                <div class="row" style="height:;">
                                    <PowerChart />
                                </div>
                                <div class="row" style="height:;">
                                    <CurrentChart />
                                </div>
                            </div>
                            <div class="col-3">
                                <div class="scrollbar scrollbar-success mb-3 bg-dark" style="height:90%;">
                                    <table class="table table-sm table-borderless mt-2">
                                        <tbody>
                                            <tr v-for="tsa in trend_select_agv" :key="tsa">
                                                <!-- <td class="text-warning p-0">·</td> -->
                                                <td scope="row"
                                                    class="text-left text-warning d-flex justify-content-between">
                                                    <ul class="mb-2">
                                                        <li>
                                                            {{ tsa.name }}
                                                        </li>
                                                    </ul>
                                                    <div class="form-check p-0 m-0">
                                                        <input type="checkbox" class="form-check-input my-0"
                                                            :checked="tsa.check">
                                                    </div>
                                                </td>
                                            </tr>
                                        </tbody>
                                    </table>
                                </div>
                                <div class="col-12 d-flex justify-content-between p-0 m-0">
                                    <button class="btn btn-sm btn-warning text-dark">SELECT ALL</button>
                                    <button class="btn btn-sm btn-primary text-dark">EXPORT EXCEL</button>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import "vue3-circle-progress/dist/circle-progress.css";
// import buttonToggle from '@/components/button/buttonToggle.vue';
import BarChart from '@/components/Chart/BarChart_TrendEnergy.vue';
import SpeedChart from '@/components/Chart/SpeedChart.vue';
import PowerChart from '@/components/Chart/PowerChart.vue';
import CurrentChart from '@/components/Chart/CurrentChart.vue';


export default {
    name: 'App',
    components: {
        // buttonToggle,
        BarChart,
        SpeedChart,
        PowerChart,
        CurrentChart,
    },
    data() {
        return {
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

/* .force-overflow-top-left {
    min-height: 450px;
}

.scrollbar-success {
    scrollbar-color: #4285F4 #F5F5F5;
}

.btn {
    width: 100%;
    height: 100%;
}

.td {
    padding: unset !important;
} */
</style>