<template>
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
</template>

<script>
import BarChart from '@/components/Chart/BarChart.vue';
export default {
    components: {
        BarChart,
    }
}
</script>

<style lang="scss" scoped>

</style>