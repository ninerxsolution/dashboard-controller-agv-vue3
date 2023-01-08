<template>
    <div class="container-fluid content bg-dark pt-3">
        <div class="row">
            <div class="col-md-4 grid-margin stretch-card">
                <div class="card">
                    <div class="card-body">
                        <h5 class>
                            CONSUMPTION
                        </h5>
                        <div class="row">
                            <div class="col-12">
                                Yeah yeah!
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-md-8 grid-margin stretch-card">
                <div class="card">
                    <div class="card-body">
                        <h5>
                            TREND YIELD AND ENEGY TOTAL
                        </h5>
                        <BarChart/>
                    </div>
                </div>
            </div>

        </div>

        <div class="row">
            <div class="col-md-4 grid-margin">
                <div class="card mb-4">
                    <div class="card-body">
                        AGV RUNNING NOW
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
export default {
    name: 'App',
    components: {
        BarChart,
    }
}
</script>

<style>
.row {
    height: 50%;
}
</style>