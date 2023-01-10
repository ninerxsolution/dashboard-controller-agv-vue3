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
                                <div>
                                    <circle-progress :percent="10" :unit="''" :show-percent="true" :size="100" class="dummy-meter"/>
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
                                    <div class="text-primary mx-3">
                                        Running
                                    </div>
                                </small>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="card mb-4">
                    <div class="card-body">
                        <h5 class="mb-0">
                            DATA AGV TRACK
                        </h5>
                        <div class="d-flex justify-content-between">
                            <ul class="list-ticked text-muted mb-0 justify-centent-between">
                                <li>
                                    <small class="text-muted d-flex justify-centent-between">
                                        Transpot today
                                    </small>
                                </li>
                            </ul>
                            <div class="text-right">
                                200/400 ton
                            </div>
                        </div>
                        <div class="d-flex justify-content-between">
                            <ul class="list-ticked text-muted mb-0 justify-centent-between">
                                <li>
                                    <small class="text-muted d-flex justify-centent-between">
                                        Working mode
                                    </small>
                                </li>
                            </ul>
                            <div class="text-right">
                                Auto
                            </div>
                        </div>
                        <div class="d-flex justify-content-between">
                            <ul class="list-ticked text-muted mb-0 justify-centent-between">
                                <li>
                                    <small class="text-muted d-flex justify-centent-between">
                                        Status cycle
                                    </small>
                                </li>
                            </ul>
                            <div class="text-right">
                                50/100 Cycle
                            </div>
                        </div>
                        <div class="d-flex justify-content-between">
                            <ul class="list-ticked text-muted mb-0 justify-centent-between">
                                <li>
                                    <small class="text-muted d-flex justify-centent-between">
                                        Maximum load
                                    </small>
                                </li>
                            </ul>
                            <div class="text-right">
                                4 ton
                            </div>
                        </div>
                        <div class="d-flex justify-content-between">
                            <ul class="list-ticked text-muted mb-0 justify-centent-between">
                                <li>
                                    <small class="text-muted d-flex justify-centent-between">
                                        Tranking guide
                                    </small>
                                </li>
                            </ul>
                            <div class="text-right">
                                camera
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-md-4 grid-margin">
                <div class="card mb-4">
                    <div class="card-body">
                        <div class="col-12 d-flex justify-content-between">
                            <h5>
                                SELECT AGV
                            </h5>
                            <div class="dropdown">
                                <button class="btn btn-light dropdown-toggle" type="button" id="dropdownMenuButton1"
                                    data-toggle="dropdown" aria-haspopup="true" aria-expanded="false"> AGV 1
                                </button>
                                <div class="dropdown-menu" aria-labelledby="dropdownMenuButton1">
                                    <h6 class="dropdown-header">AGV</h6>
                                    <a class="dropdown-item" href="#">AGV 1</a>
                                    <a class="dropdown-item" href="#">AGV 2</a>
                                    <a class="dropdown-item" href="#">AGV 3</a>
                                    <a class="dropdown-item" href="#">AGV 4</a>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="card mb-4">
                    <div class="card-body">
                        <h5 class="text-center">
                            AGV ICON
                        </h5>
                    </div>
                </div>
                <div class="card mb-4">
                    <div class="card-body">
                        <h5>
                            BATTERY CAPACITY
                        </h5>
                        <div class="d-flex justify-content-between">
                            <div class="progress mt-1" style="height:2rem !important;">
                                <div class="progress-bar bg-success" role="progressbar" style="width: 82.1%;"
                                    aria-valuenow="90" aria-valuemin="0" aria-valuemax="100">
                                </div>
                            </div>
                            <div class="text-right h2">
                                82.1 %
                            </div>
                        </div>
                        <div class="text text-sm text-center text-warning">
                            Discharge
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-md-4 grid-margin">
                <div class="card mb-4">
                    <div class="card-body">
                        <h5>
                            ELECTRICAL VOLTAGE AGV
                        </h5>
                        <div class="row">
                            <div class="col-6 text-center">
                                <div>
                                    <circle-progress :percent="80" :unit="kg / hr" :show-percent="true" :size="100"
                                        :fill-color="'#ffd000'" class="dummy-meter"/>
                                </div>
                                <div class="pt-1 text-muted">
                                    <small>
                                        VOLTAGE AVERAGE
                                    </small>
                                </div>
                            </div>
                            <div class="col-6">
                                <div class="display-4">
                                    50.6 v
                                </div>
                                <small>
                                    VOL MAX 55.9 v
                                </small><br>
                                <small>
                                    VOL MIN 48.9 v
                                </small><br>
                                <small class="d-flex">
                                    STATUS
                                    <div class="mx-3 text-warning">
                                        Standby
                                    </div>
                                </small>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="card mb-4">
                    <div class="card-body">
                        <h5>
                            AGV RUNNING NOW
                        </h5>
                        <div class="row">
                            <div class="col-6 text-center">
                                <div>
                                    <circle-progress :percent="80" :unit="kg / hr" :show-percent="true" :size="100"
                                        :class="circle - progress" class="dummy-meter"/>
                                </div>
                                <div class="pt-1 text-muted">
                                    <small>
                                        SPEED CURRENT
                                    </small>
                                </div>
                            </div>
                            <div class="col-6">
                                <div class="display-4">
                                    49.9 A
                                </div>
                                <small>
                                    CURRENT MAX 120.0
                                </small><br>
                                <small>
                                    CURRENT AVE 35.0
                                </small><br>
                                <small class="d-flex">
                                    STATUS
                                    <div class="text-warning mx-3">
                                        Forward
                                    </div>
                                </small>
                                <small class="d-flex">
                                    WORKING
                                    <div class="text-primary mx-3">
                                        Ready
                                    </div>
                                </small>
                            </div>
                        </div>
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
        width: 70%;
        color: #ffd000;
    }
}
</style>