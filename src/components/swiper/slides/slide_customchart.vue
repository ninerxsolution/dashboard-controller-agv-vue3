<template>
    <div class="container-fluid content bg-dark pt-3">
        <div class="row">
            <div class="col-md-4 grid-margin stretch-card">
                <div class="card">
                    <div class="card-body">
                        <h5>
                            CONNECT AGV
                        </h5>
                        <div class="row">
                            <div class="d-flex justify-content-between">
                                <ul class="list-ticked text-muted mb-0">
                                    <li>
                                        <small class="text-muted">
                                            TOTAL AGV
                                        </small>
                                    </li>
                                </ul>
                                <div class="progress mt-1" style="width: 40%">
                                    <div class="progress-bar bg-warning" role="progressbar" style="width: 100%"
                                        aria-valuenow="100" aria-valuemin="0" aria-valuemax="100">
                                    </div>
                                </div>
                                <div class="text-right mx-1">
                                    3
                                </div>
                            </div>
                            <div class="d-flex justify-content-between">
                                <ul class="list-ticked text-muted mb-0">
                                    <li>
                                        <small class="text-muted">
                                            AGV Online
                                        </small>
                                    </li>
                                </ul>
                                <div class="progress mt-1" style="width: 40%">
                                    <div class="progress-bar bg-success" role="progressbar" style="width: 33%"
                                        aria-valuenow="100" aria-valuemin="0" aria-valuemax="100">
                                    </div>
                                </div>
                                <div class="text-right mx-1">
                                    1
                                </div>
                            </div>
                            <div class="d-flex justify-content-between">
                                <ul class="list-ticked text-muted mb-0">
                                    <li>
                                        <small class="text-muted">
                                            AGV Offline
                                        </small>
                                    </li>
                                </ul>
                                <div class="progress mt-1" style="width: 40%">
                                    <div class="progress-bar bg-danger" role="progressbar" style="width: 66%"
                                        aria-valuenow="100" aria-valuemin="0" aria-valuemax="100">
                                    </div>
                                </div>
                                <div class="text-right mx-1">
                                    2
                                </div>
                            </div>
                            <div class="pt-1 text-danger text-center">
                                <small>
                                    For Maximum AGV : 3 connects
                                </small>
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
                                DETAIL PARAMETER AGV
                            </h5>
                            <div class="text-success">
                                <small>
                                    Enegy (kWh) : 54376
                                </small>
                            </div>
                            <div class="text-danger">
                                <small>
                                    CO2 (kg) : 3456
                                </small>
                            </div>
                            <div class="text">

                            </div>
                            <div class="progress mt-1" style="width: 10%">
                                <div class="progress-bar bg-success" role="progressbar" style="width: 66%"
                                    aria-valuenow="100" aria-valuemin="0" aria-valuemax="100">
                                    81.2%
                                </div>
                            </div>
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
                        <div class="row mt-3">
                            <div class="col-3">
                                <div class="justify-content-between">
                                    <circle-progress :percent="15" :unit="kg / hr" :show-percent="false" :size="100"
                                        :fill-color="'#89b8e0'" class="dummy-meter" />
                                </div>
                                <div class="pt-1 text-muted text-center">
                                    <small>
                                        Current speed
                                    </small>
                                </div>
                                <div class="h3 mb-0 text-center">
                                    0.5 m/s
                                </div>
                                <div class="text-primary text-center">
                                    <small>
                                        Running
                                    </small>
                                </div>
                            </div>
                            <div class="col-3">
                                <div class="justify-content-between">
                                    <circle-progress :percent="80" :unit="kg / hr" :show-percent="false" :size="100"
                                        :fill-color="'#ffd000'" class="dummy-meter" />
                                </div>
                                <div class="pt-1 text-muted text-center">
                                    <small>
                                        Voltage average
                                    </small>
                                </div>
                                <div class="h3 mb-0 text-center">
                                    50.6 V
                                </div>
                                <div class="text-warning text-center">
                                    <small>
                                        Standby
                                    </small>
                                </div>
                            </div>
                            <div class="col-3">
                                <div class="justify-content-between">
                                    <circle-progress :percent="80" :unit="kg / hr" :show-percent="false" :size="100"
                                        :fill-color="'#00a2ff'" class="dummy-meter" />
                                </div>
                                <div class="pt-1 text-muted text-center">
                                    <small>
                                        Current now
                                    </small>
                                </div>
                                <div class="h3 mb-0 text-center">
                                    49.9 A
                                </div>
                                <div class="text-primary text-center">
                                    <small>
                                        Ready
                                    </small>
                                </div>
                            </div>
                            <div class="col-3">
                                <div class="justify-content-between">
                                    <circle-progress :percent="45" :unit="kg / hr" :show-percent="false" :size="100"
                                        :fill-color="'#4cff45'" class="dummy-meter" />
                                </div>
                                <div class="pt-1 text-muted text-center">
                                    <small>
                                        Power now
                                    </small>
                                </div>
                                <div class="h3 mb-0 text-center">
                                    2.5 kW
                                </div>
                                <div class="text-success text-center">
                                    <small>
                                        Using
                                    </small>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="row">
            <div class="col-md-12 grid-margin stretch-card">
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
                        <CustomChart />
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import "vue3-circle-progress/dist/circle-progress.css";
import CircleProgress from "vue3-circle-progress";
import CustomChart from '@/components/Chart/CustomChart.vue';

export default {
    name: 'App',
    components: {
        CircleProgress,
        CustomChart,
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
</style>