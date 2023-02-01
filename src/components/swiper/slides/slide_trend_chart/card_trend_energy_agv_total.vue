<template>
    <div class="card">
        <div class="card-body">
            <div class="col-12 d-flex justify-content-between">
                <h5 class="d-flex">
                    TREND ENERGY AND AGV TOTAL
                </h5>
                <div class="text d-flex">
                    <div class="col-sm-6 h6 text-right m-0 align-self-center">SELECT TYPE:</div>
                    <div class="col-sm-6 text-warning pt-0">
                        <div class="input-group-prependtop-left align-self-center">
                            <button class="btn btn-link dropdown-toggle text-warning  align-self-center" type="button"
                                data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                                ENERGY & YIELD
                            </button>
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
            <BarChart />
        </div>
    </div>
</template>

<script>
import BarChart from '@/components/Chart/BarChart_TrendEnergy.vue';

export default {
    components: {
        BarChart,
    }
}
</script>

<style lang="scss" scoped>

</style>