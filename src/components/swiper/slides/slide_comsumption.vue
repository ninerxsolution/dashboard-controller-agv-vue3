<template>
    <div class="container-fluid content bg-dark pt-3">
        <div class="row">
            <div class="col-md-4 grid-margin stretch-card">
                <div class="card">
                    <div class="card-body">
                        <h5>
                            CONSUMPTION PRODUCTION TOTAL
                        </h5>
                        <div class="row">
                            <div class="col-12">
                                <ul class="list-ticked text-muted mb-0">
                                    <li>
                                        <small class="text-muted">
                                            PRODUCTION TOTAL (ton)
                                        </small>
                                    </li>
                                </ul>
                                <div class="d-flex justify-content-between">
                                    <div class="progress mt-1">
                                        <div class="progress-bar bg-warning" role="progressbar" style="width: 10%"
                                            aria-valuenow="90" aria-valuemin="0" aria-valuemax="100">
                                        </div>
                                    </div>
                                    <div class="text-right h6">
                                        50 ton
                                    </div>
                                </div>
                            </div>
                            <div class="col-12">
                                <ul class="list-ticked text-muted mb-0">
                                    <li>
                                        <small class="text-muted">
                                            ENERGY (kWh)
                                        </small>
                                    </li>
                                </ul>
                                <div class="d-flex justify-content-between">
                                    <div class="progress mt-1">
                                        <div class="progress-bar bg-primary" role="progressbar" style="width: 80%"
                                            aria-valuenow="90" aria-valuemin="0" aria-valuemax="100">
                                        </div>
                                    </div>
                                    <div class="text-right h6">
                                        6069 kWh
                                    </div>
                                </div>
                            </div>
                            <div class="col-12">
                                <ul class="list-ticked text-muted mb-0">
                                    <li>
                                        <small class="text-muted">
                                            BATTERY (kWh)
                                        </small>
                                    </li>
                                </ul>
                                <div class="d-flex justify-content-between">
                                    <div class="progress mt-1">
                                        <div class="progress-bar bg-success" role="progressbar" style="width: 65%"
                                            aria-valuenow="90" aria-valuemin="0" aria-valuemax="100">
                                        </div>
                                    </div>
                                    <div class="text-right h6">
                                        562 kWh
                                    </div>
                                </div>
                            </div>
                            <div class="col-12">
                                <ul class="list-ticked text-muted mb-0">
                                    <li>
                                        <small class="text-muted">
                                            CO2 (kg)
                                        </small>
                                    </li>
                                </ul>
                                <div class="d-flex justify-content-between">
                                    <div class="progress mt-1">
                                        <div class="progress-bar bg-danger" role="progressbar" style="width: 75%"
                                            aria-valuenow="90" aria-valuemin="0" aria-valuemax="100">
                                        </div>
                                    </div>
                                    <div class="text-right h6">
                                        4061 kg
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-md-8 grid-margin stretch-card">
                <div class="card">
                    <div class="card-body">

                        <div class="col-12 d-flex justify-content-between">
                            <h5 class="d-flex">
                                TREND YIELD AND ENEGY TOTAL
                            </h5>
                            <div class="btn-group d-flex" role="group" aria-label="Basic example">
                                <button type="button" class="btn btn-outline-secondary">
                                    Year </button>
                                <button type="button" class="btn btn-outline-secondary">
                                    Month </button>
                                <button type="button" class="btn btn-outline-secondary">
                                    Week </button>
                            </div>
                        </div>
                        <BarChart />

                    </div>
                </div>
            </div>

        </div>

        <div class="row">
            <div class="col-md-4 grid-margin">
                <div class="card mb-4">
                    <div class="card-body">
                        <h5>
                            AGV RUNNING NOW
                        </h5>
                        <div class="row">
                            <div class="col-6 text-center">
                                <!-- <div class="meter-dummy" style="width:170px; height:120px; background-color:white;">
                                </div> -->
                                <div>
                                    <circle-progress :percent="40" :unit="kg / hr" :show-percent="true" :size="140"
                                        :class="circle - progress" />
                                </div>
                                <div class="pt-1 text-muted">
                                    <small>
                                        SPEED CURRENT
                                    </small>
                                </div>
                            </div>
                            <div class="col-6">
                                <div class="display-4">
                                    0.5 m/s
                                </div>
                                <small>
                                    SPEED MAX 2.0 m/s
                                </small><br>
                                <small>
                                    SET SPEED 0.5 m/s
                                </small><br>
                                <small class="d-flex">
                                    STATUS
                                    <div class="text-muted mx-3">
                                        Running
                                    </div>
                                </small>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="card mb-4">
                    <div class="card-body">
                        DATA AGV
                    </div>
                </div>
            </div>
            <div class="col-md-4 grid-margin">
                <div class="card mb-4">
                    <div class="card-body">
                        SELECT AGV
                    </div>
                </div>
                <div class="card mb-4">
                    <div class="card-body">
                        IMG
                    </div>
                </div>
                <div class="card mb-4">
                    <div class="card-body">
                        BATTERY CAPACITY
                    </div>
                </div>
            </div>
            <div class="col-md-4 grid-margin">
                <div class="card mb-4">
                    <div class="card-body">
                        VOLT AGV
                    </div>
                </div>
                <div class="card mb-4 ">
                    <div class="card-body">
                        MOTOR
                    </div>
                </div>

            </div>
        </div>

    </div>
</template>

<script>
import BarChart from '@/components/Chart/BarChart.vue';

import "vue3-circle-progress/dist/circle-progress.css";
import CircleProgress from "vue3-circle-progress";

export default {
    name: 'App',
    components: {
        BarChart,
        CircleProgress,
    }
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
        width: 70%
    }
}
</style>