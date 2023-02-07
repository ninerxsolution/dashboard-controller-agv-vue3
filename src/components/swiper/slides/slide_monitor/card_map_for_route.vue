<template>
    <div class="card  mb-4">
        <div class="card-body">

            <div class="d-flex justify-content-between">
                <h5 class="d-flex mb-0 mt-1">
                    <span>MAP FOR ROUTE</span>
                </h5>
                <div class="d-flex">
                    <button class="btn-dark text-warning">
                        <div>
                            Non drawback AGV 1
                        </div>
                    </button>
                    <i class="mdi mdi-eye px-2  align-self-center"></i>
                    <button class="btn-dark text-success">
                        <div>
                            Battery AGV 1 OK
                        </div>
                    </button>
                    <i class="mdi mdi-truck px-2  align-self-center"></i>
                </div>

                <div class="d-flex">
                    <div class="text align-self-center">
                        CONNECT :
                    </div>
                    <button-toggle class="mx-2 align-self-center" />
                    <button class="btn btn-warning text-dark mx-2 px-4">
                        UPDATE MAP
                    </button>
                </div>
            </div>
            <div class="row">
                <div class="col-12 mt-4">
                    <div class="card-body bg-dark p-2">
                        <div class="card-title d-flex justify-content-between">
                            <div>
                                Point Station
                            </div>
                            <div>
                                Point End
                            </div>
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

                <div class="d-flex justify-content-between mt-3">
                    <div class="col-3 bg-dark mt-4 p-4">

                        <div class="d-flex align-self-middle">
                            <ul class="m-0">
                                <li>
                                    <div class="align-self-middle">
                                        <span class="">AGV 1</span>
                                    </div>
                                </li>
                            </ul>
                            <div class="text-success align-self-middle">
                                <div class="div mx-4 align-self-middle">
                                    <span>Running</span>
                                </div>
                            </div>
                        </div>

                        <div class="d-flex align-self-middle">
                            <ul class="mb-0">
                                <li>
                                    <div>
                                        <span>AGV 2</span>
                                    </div>
                                </li>
                            </ul>
                            <div class="text-danger">
                                <div class="div mt-1 mx-4">
                                    <span> Offline</span>
                                </div>
                            </div>
                        </div>
                        <div class="d-flex align-self-middle">
                            <ul class="mb-0">
                                <li>
                                    <div>
                                        <span>AGV 3</span>
                                    </div>
                                </li>
                            </ul>
                            <div class="text-danger">
                                <div class="div mt-1 mx-4">
                                    <span>Offline</span>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="col-3 bg-dark mt-4 p-4">
                        <div class="d-flex ">
                            <ul class="mb-0">
                                <li>
                                    <div>
                                        <span> AGV 1</span>
                                    </div>
                                </li>
                            </ul>
                            <div class="text-primary m-0">
                                <div class="div mt-1 mx-4">
                                    <span>200 ton</span>
                                </div>
                            </div>
                        </div>
                        <div class="d-flex">
                            <ul class="mb-0">
                                <li>
                                    <div>
                                        <span>AGV 2</span>
                                    </div>
                                </li>
                            </ul>
                            <div class="text-warning">
                                <div class="div mt-1 mx-4">
                                    <span>0 ton</span>
                                </div>
                            </div>
                        </div>
                        <div class="d-flex">
                            <ul class="mb-0">
                                <li>
                                    <div>
                                        <span> AGV 3</span>
                                    </div>
                                </li>
                            </ul>
                            <div class="text-warning">
                                <div class="div mt-1 mx-4">
                                    <span> 0 ton</span>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="col-3  bg-dark pt-4">
                        <div class="d-flex">
                            <ul class="mb-0">
                                <li>
                                    <div>
                                        <span>AGV 1</span>
                                    </div>
                                </li>
                            </ul>
                            <div class="text-primary">
                                <div class="div mt-1 mx-4">
                                    <span>200 ton</span>
                                </div>
                            </div>
                        </div>
                        <div class="d-flex">
                            <ul class="mb-0">
                                <li>
                                    <div>
                                        <span>AGV 2</span>
                                    </div>
                                </li>
                            </ul>
                            <div class="text-warning">
                                <div class="div mt-1 mx-4">
                                    <span>0 ton</span>
                                </div>
                            </div>
                        </div>
                        <div class="d-flex">
                            <ul class="mb-0">
                                <li>
                                    <div>
                                        <span>AGV 3</span>
                                    </div>
                                </li>
                            </ul>
                            <div class="text-warning">
                                <div class="div mt-1 mx-4">
                                    <span> 0 ton</span>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="col-3  bg-dark pt-4">
                        <div class="d-flex text-warning justify-content-between">
                            <ul class="mb-0">
                                <li>
                                    <div>
                                        <span> DISTANCE TOTAL</span>
                                    </div>
                                </li>
                            </ul>
                            <div class="text-right">
                                <div class="div mt-1 mx-2">
                                    500 m
                                </div>
                            </div>
                        </div>
                        <div class="d-flex text-primary justify-content-between">
                            <ul class="mb-0">
                                <li>
                                    <div>
                                        <span>MAXIMUM CYCLE</span>
                                    </div>
                                </li>
                            </ul>
                            <div class="text-right">
                                <div class="div mt-1 mx-2">
                                    10 min
                                </div>
                            </div>
                        </div>
                        <div class="d-flex text-warning justify-content-between">
                            <ul class="mb-0">
                                <li>
                                    <div>
                                        <span>MAXIMUX SPEED</span>
                                    </div>
                                </li>
                            </ul>
                            <div class="text-right">
                                <div class="div mt-1 mx-2">
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