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
            <div class="col-12 grid-margin">
                <div class="card mb-4">
                    <div class="card-body">

                        <div class="d-flex justify-content-between">
                            <h5 class="d-flex mb-0 mt-1">
                                MAP FOR ROUTE
                            </h5>
                            <div class="d-flex">
                                <button class="btn-dark text-warning">
                                    <small>
                                        Non drawback AGV 1
                                    </small>
                                </button>
                                <i class="mdi mdi-eye px-2"></i>
                                <button class="btn-dark text-success">
                                    <small>
                                        Battery AGV 1 OK
                                    </small>
                                </button>
                                <i class="mdi mdi-truck px-2"></i>
                            </div>

                            <div class="d-flex">
                                <div class="text">
                                    CONNECT :
                                </div>
                                <button-toggle class="mx-2 mt-1" />
                                <button class="btn btn-warning text-dark mx-2 px-4">
                                    UPDATE MAP
                                </button>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-12 mt-2">
                                <div class="card-body bg-dark p-2">
                                    <div class="card-title d-flex justify-content-between">
                                        <small>
                                            Point Station
                                        </small>
                                        <small>
                                            Point End
                                        </small>
                                    </div>
                                    <div class="d-flex justify-content-between">
                                        <ul>
                                            <li>
                                                AGV 1
                                            </li>
                                        </ul>
                                        <div class="progress mt-1 mx-3" style="width:85%;">
                                            <div class="progress-bar bg-warning" style="width:47%;">
                                                <div class="text-dark">
                                                    AGV 1 Running : SPEED 0.5 m/s
                                                </div>
                                            </div>
                                        </div>
                                    </div>
                                    <div class="d-flex justify-content-between">
                                        <ul>
                                            <li>
                                                AGV 2
                                            </li>
                                        </ul>
                                        <div class="progress mt-1 mx-3" style="width:85%;">
                                            <div class="progress-bar bg-warning" style="width:0%;">
                                            </div>
                                        </div>
                                    </div>
                                    <div class="d-flex justify-content-between">
                                        <ul>
                                            <li>
                                                AGV 3
                                            </li>
                                        </ul>
                                        <div class="progress mt-1 mx-3" style="width:85%;">
                                            <div class="progress-bar bg-warning" style="width:0%;">

                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                            <div class="d-flex justify-content-between">
                                <div class="col-2 card-body bg-dark mt-2">
                                    <div class="d-flex">
                                        <ul class="mb-0">
                                            <li>
                                                <div class="h6">
                                                    AGV 1
                                                </div>
                                            </li>
                                        </ul>
                                        <div class="text-success">
                                            <div class="small mt-1 mx-2">
                                                Running
                                            </div>
                                        </div>
                                    </div>
                                    <div class="d-flex">
                                        <ul class="mb-0">
                                            <li>
                                                <div class="h6">
                                                    AGV 2
                                                </div>
                                            </li>
                                        </ul>
                                        <div class="text-danger">
                                            <div class="small mt-1 mx-2">
                                                Offline
                                            </div>
                                        </div>
                                    </div>
                                    <div class="d-flex">
                                        <ul class="mb-0">
                                            <li>
                                                <div class="h6">
                                                    AGV 3
                                                </div>
                                            </li>
                                        </ul>
                                        <div class="text-danger">
                                            <div class="small mt-1 mx-2">
                                                Offline
                                            </div>
                                        </div>
                                    </div>
                                </div>

                                <div class="col-2 card-body bg-dark mt-2 pt-4">
                                    <div class="d-flex">
                                        <ul class="mb-0">
                                            <li>
                                                <div class="h6">
                                                    AGV 1
                                                </div>
                                            </li>
                                        </ul>
                                        <div class="text-primary">
                                            <div class="small mt-1 mx-2">
                                                200 ton
                                            </div>
                                        </div>
                                    </div>
                                    <div class="d-flex">
                                        <ul class="mb-0">
                                            <li>
                                                <div class="h6">
                                                    AGV 2
                                                </div>
                                            </li>
                                        </ul>
                                        <div class="text-warning">
                                            <div class="small mt-1 mx-2">
                                                0 ton
                                            </div>
                                        </div>
                                    </div>
                                    <div class="d-flex">
                                        <ul class="mb-0">
                                            <li>
                                                <div class="h6">
                                                    AGV 3
                                                </div>
                                            </li>
                                        </ul>
                                        <div class="text-warning">
                                            <div class="small mt-1 mx-2">
                                                0 ton
                                            </div>
                                        </div>
                                    </div>
                                </div>
                                <div class="col-2 card-body bg-dark mt-2 pt-4">
                                    <div class="d-flex">
                                        <ul class="mb-0">
                                            <li>
                                                <div class="h6">
                                                    AGV 1
                                                </div>
                                            </li>
                                        </ul>
                                        <div class="text-primary">
                                            <div class="small mt-1 mx-2">
                                                200 ton
                                            </div>
                                        </div>
                                    </div>
                                    <div class="d-flex">
                                        <ul class="mb-0">
                                            <li>
                                                <div class="h6">
                                                    AGV 2
                                                </div>
                                            </li>
                                        </ul>
                                        <div class="text-warning">
                                            <div class="small mt-1 mx-2">
                                                0 ton
                                            </div>
                                        </div>
                                    </div>
                                    <div class="d-flex">
                                        <ul class="mb-0">
                                            <li>
                                                <div class="h6">
                                                    AGV 3
                                                </div>
                                            </li>
                                        </ul>
                                        <div class="text-warning">
                                            <div class="small mt-1 mx-2">
                                                0 ton
                                            </div>
                                        </div>
                                    </div>
                                </div>

                                <div class="col-3 card-body bg-dark mt-2">
                                    <div class="d-flex text-warning justify-content-between">
                                        <ul class="mb-0">
                                            <li>
                                                <div class="h5">
                                                    DISTANCE TOTAL
                                                </div>
                                            </li>
                                        </ul>
                                        <div class="text-right">
                                            <div class="small mt-1 mx-2">
                                                500 m
                                            </div>
                                        </div>
                                    </div>
                                    <div class="d-flex text-primary justify-content-between">
                                        <ul class="mb-0">
                                            <li>
                                                <div class="h5">
                                                    MAXIMUM CYCLE
                                                </div>
                                            </li>
                                        </ul>
                                        <div class="text-right">
                                            <div class="small mt-1 mx-2">
                                                10 min
                                            </div>
                                        </div>
                                    </div>
                                    <div class="d-flex text-warning justify-content-between">
                                        <ul class="mb-0">
                                            <li>
                                                <div class="h5">
                                                    MAXIMUX SPEED
                                                </div>
                                            </li>
                                        </ul>
                                        <div class="text-right">
                                            <div class="small mt-1 mx-2">
                                                2 m/s
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
import CircleProgress from "vue3-circle-progress";
import buttonToggle from '@/components/button/buttonToggle.vue';

export default {
    name: 'App',
    components: {
        CircleProgress,
        buttonToggle,
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