<template>
    <div class="container-fluid content d-flex flex-column justify-content-strat bg-dark py-4">
        <div class="container">
            <div class="row">
                <div class="col-lg-4 grid-margin stretch-card">
                    <card-top-left></card-top-left>
                </div>
                <div class="col-lg-8 grid-margin stretch-card">
                    <div class="card">
                        <div class="container m-0 p-0">
                            <div class="card-body card-height-medium pt-0">
                                <div class="container">
                                    <div class="row">
                                        <div class="col-5 h6 pt-2">TREND ENERGY AGV TOTAL</div>
                                        <div class="col-7 h6">
                                            <div class="row">
                                                <div class="col-sm-6 h6 pt-2 text-right">SELECT TYPE:</div>
                                                <div class="col-sm-6 text-warning">
                                                    <div class="input-group-prependtop-left">
                                                        <button class="btn btn-link dropdown-toggle text-warning pt-2" type="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">ENERGY & YIELD</button>
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
                                    </div>
                                </div>
                                <BarChart />
                                <div class="d-flex flex-row justify-content-end pt-2">
                                    <div>
                                        <button class="btn btn-sm btn-dark btn-rounded mx-2 ">year</button>
                                    </div>
                                    <div>
                                        <button class="btn btn-sm btn-dark btn-rounded mx-2 ">month</button>
                                    </div>
                                    <div>
                                        <button class="btn btn-sm btn-dark btn-rounded mx-2 ">day</button>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="container">
            <div class="row">
                <div class="col-lg-8 grid-margin stretch-card">
                    <card-bottom-left/>
                </div>
                <div class="col-lg-4 grid-margin stretch-card">
                    <card-bottom-right/>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import BarChart from '@/components/Chart/BarChart.vue';
import CardBottomRight from './slide_trendChart/CardBottomRight.vue';
import CardBottomLeft from './slide_trendChart/CardBottomLeft.vue';
import CardTopLeft from './slide_trendChart/CardTopLeft.vue'
// import LineChart from '@/components/Chart/LineChart.vue';
export default{
    components: {
        CardBottomRight,
        BarChart,
        CardBottomLeft,
        CardTopLeft,
        // LineChart,
    },
}
</script>

<style>
.card-height-medium{
    height:220px;
} 
.input-group-prepend .top-left{
    width:100%;
    height:100%;
    background-color: #fff !important;
}

</style>