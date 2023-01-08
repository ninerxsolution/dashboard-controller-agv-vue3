<template>
    <div class="container-fluid content bg-dark pt-3">
        <div class="row">
            // Basic Usage
            <circle-progress :percent="40" />

            // Default Gradient
            <circle-progress :is-gradient="true" />

            // Customize Gradient
            <circle-progress :is-gradient="true" :gradient="{
                angle: 90,
                startColor: '#ff0000',
                stopColor: '#ffff00'
            }" />

            // Default Shadow
            <circle-progress :is-bg-shadow="true" />

            // Customize Shadow
            <circle-progress :is-bg-shadow="true" :bg-shadow="{
                inset: true,
                vertical: 2,
                horizontal: 2,
                blur: 4,
                opacity: .4,
                color: '#000000'
            }" empty-color="#f7f7f7" :border-width="6" :border-bg-width="30" />
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
                            <div class="col-7">
                                <!-- <div class="meter-dummy" style="width:170px; height:120px; background-color:white;">

                                </div> -->

                            </div>
                            <div class="col-5">

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