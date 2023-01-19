<template>
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
</template>

<script>
import buttonToggle from '@/components/button/buttonToggle.vue';

export default {
    components: {
        buttonToggle,
    }
}
</script>

<style lang="scss" scoped>

</style>