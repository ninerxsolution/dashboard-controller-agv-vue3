<template>
    <div class="container-fluid content bg-dark pt-3">
        <div class="row">
            <div class="col-md-5 grid-margin stretch-card">
                <div class="card">
                    <div class="card-body">

                        <h5>
                            CONFIRM RUNNING SYSTEM
                        </h5>

                        <div class="d-flex justify-content-around bg-dark p-3">
                            <div class="start-big-button bg-success">
                                <div class="h2">
                                    start
                                </div>
                            </div>
                            <div class="stop-big-button bg-danger">
                                <div class="h2">
                                    stop
                                </div>
                            </div>

                        </div>
                        <div class="d-flex justify-content-center p-3">
                            <div class="mx-3">
                                <button class="btn btn-inverse-light text-warning">
                                    STATUS: <small>Running</small>
                                </button>
                            </div>
                            <div class="mt-2">
                                <ButtonToggle />
                            </div>
                            <div class="h6 text-warning mt-2 mx-3">
                                CONFIRM
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <div class="col-md-7 grid-margin stretch-card">
                <div class="card">
                    <div class="card-body">
                        <h5 class="d-flex">
                            SET PARAMETER SYSTEM
                        </h5>
                        <div class="col-12">
                            <div class="scrollbar scrollbar-setting-setpara" style="height:10rem;">
                                <table class="table table-sm table-borderless force-overflow-setting mt-2">
                                    <tbody>
                                        <tr v-for="sps in set_param_sys" :key="sps">
                                            <td scope="row" class="text-left text-warning p-0">
                                                <ul class="mb-2">
                                                    <li>
                                                        {{ sps.name_left }}
                                                    </li>
                                                </ul>
                                            </td>
                                            <td class="text-center text-primary sup-val">
                                                <div class="val bg-dark p-2">
                                                    {{ sps.val_left }}
                                                </div>
                                            </td>
                                            <td class="space"></td>
                                            <td scope="row" class="text-left text-warning p-0">
                                                <ul>
                                                    <li>
                                                        {{ sps.name_right }}
                                                    </li>
                                                </ul>
                                            </td>
                                            <td class="text-center text-primary sup-val">
                                                <div class="val bg-dark p-2">
                                                    {{ sps.val_right }}
                                                </div>
                                            </td>
                                        </tr>
                                    </tbody>
                                </table>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <div class="row">
            <div class="col-12 grid-margin">
                <div class="card mb-4">
                    <div class="card-body">
                        <div class="row px-2">
                            <div class="col-9 d-flex justify-content-started px-0">
                                <div class="d-flex h5 mx-0 mt-1">
                                    SET PARAMETER AGV
                                </div>
                                <div class="d-flex">
                                    <div class="btn btn-dark text text-warning mx-3">
                                        CONFIRM STANDBY AGV 1
                                    </div>
                                </div>
                            </div>
                            <div class="col-3 d-flex px-3">
                                OPTION
                            </div>
                        </div>

                        <div class="row">
                            <div class="col-9 mt-2">
                                <div class="agv-set-param" v-for="cl in car_list" :key="cl">
                                    <com-set-param :name="cl.name" :speed="cl.speed" :battery="cl.battery" />
                                </div>
                            </div>
                            <div class="col-3 bg-dark d-flex">
                                <div class="d-flex flex-column justify-content-around card-option-content">
                                    <div class="text-primary text-center"><small>WORNNING REPORT</small></div>
                                    <div class="app-option">
                                        <div class="container card-option-content">
                                            <div class="row option-item-row">
                                                <div class="col-md-6 d-flex flex-column justify-content-center">
                                                    <div>
                                                        <img class="img-social"
                                                            src="https://static.newmobilelife.com/wp-content/uploads/2014/10/LineforiPad00-210x210.png"
                                                            alt="">
                                                    </div>
                                                </div>
                                                <div
                                                    class="col-md-6 d-flex flex-column justify-content-center text-center">
                                                    <div class="text-warning mb-2"><small>LINE APP</small> </div>
                                                    <div class="mb-2 mx-4"><button-toggle /></div>
                                                    <div class="text-warning"><small>CONFIRM</small> </div>
                                                </div>
                                            </div>
                                        </div>
                                    </div>
                                    <div class="app-option">
                                        <div class="container card-option-content">
                                            <div class="row option-item-row">
                                                <div class="col-md-6 d-flex flex-column justify-content-center">
                                                    <div>
                                                        <img class="img-social"
                                                            src="https://logos-download.com/wp-content/uploads/2016/05/Gmail_logo_icon.png"
                                                            alt="">
                                                    </div>
                                                </div>
                                                <div
                                                    class="col-md-6 d-flex flex-column justify-content-center text-center">
                                                    <div class="text-warning mb-2"><small>GMAIL</small> </div>
                                                    <div class="mb-2 mx-4"><button-toggle /></div>
                                                    <div class="text-warning"><small>CONFIRM</small> </div>
                                                </div>
                                            </div>
                                        </div>
                                    </div>
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

import ButtonToggle from '@/components/button/buttonToggle.vue';
import ComSetParam from './slide_setting/ComSetParam.vue';

export default {
    name: 'App',
    components: {
        // buttonToggle,
        ButtonToggle,
        ComSetParam,
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

            ],
            set_param_sys: [
                { name_left: 'AGV', val_left: '1', name_right: 'PRODUCTION', val_right: '400 ton.' },
                { name_left: 'MAX SPEED', val_left: '2 m/s', name_right: 'MAX LOAD', val_right: '4 ton.' },
                { name_left: 'CYCLE TIME', val_left: '10 min.', name_right: 'LOOP CYCLE', val_right: '100 cyc.' },
                { name_left: 'DISTANCE', val_left: '500 m', name_right: 'CAMERA', val_right: 'YES' },
                { name_left: 'BATTERY TIME', val_left: '8 hour', name_right: 'LIDAR', val_right: 'YES' },
                { name_left: 'test', val_left: '0', name_right: 'test', val_right: '0' },
                { name_left: 'test', val_left: '0', name_right: 'test', val_right: '0' },
                { name_left: 'test', val_left: '0', name_right: 'test', val_right: '0' },
            ],
            car_list: [
                { name: 'AGV 1', speed: '2 m/s', battery: '25 %' },
                { name: 'AGV 2', speed: '0 m/s', battery: '0 %' },
                { name: 'AGV 3', speed: '0 m/s', battery: '0 %' },
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
.scrollbar-top-left {
    /* margin-left: 30px; */
    /* float: left; */
    height: 8rem;
    /* width: 65px; */
    /* background: #fff; */
    overflow-y: scroll;
    margin-bottom: 25px;
}


.scrollbar-success::-webkit-scrollbar {
    width: 10px;
    background-color: #000000;
}

.scrollbar-success::-webkit-scrollbar-thumb {
    border-radius: 20px;
    -webkit-box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.1);
    background-color: #ffffff;
}

.start-stop-button-area {
    height: 120px;
}

.start-big-button {
    width: 90px;
    height: 90px;
    margin-top: auto;
    margin-bottom: auto;
    border: solid 4px gray;
    border-radius: 50%;
    text-align: center;
    padding-top: 1.25rem;
}

.stop-big-button {
    width: 90px;
    height: 90px;
    margin-top: auto;
    margin-bottom: auto;
    border: solid 4px gray;
    border-radius: 50%;
    text-align: center;
    padding-top: 1.25rem;
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