<template>
    <div class="card">
        {{ get_TREND_CHART.monthly }}
        <div class="card-body">
            <div class="col-12 d-flex justify-content-between">
                <h5 class="d-flex">
                    TREND YIELD AND ENEGY TOTAL
                </h5>
                <div class="btn-group d-flex" role="group" aria-label="Basic example">
                    <!-- <button type="button" class="btn btn-outline-secondary">
                        Year 
                    </button> -->
                    <button type="button" class="btn btn-outline-secondary" @click="changeChart('Month')">
                        Month
                    </button>
                    <button type="button" class="btn btn-outline-secondary" @click="changeChart('Day')">
                        Day
                    </button>
                    {{ change_chart_check }}
                </div>
            </div>
            <BarChart :get_CHART_DATA="Default" />
        </div>
    </div>
</template>

<script>
import BarChart from '@/components/Chart/BarChart.vue';
export default {
    components: {
        BarChart,
    },
    data() {
        return {
            change_chart_check: 'Un checkable',
        }
    },
    props: {
        get_TREND_CHART: {
            type: String,
        }
    },
    created() {
        setInterval(() => {
            this.thrower_first()
            setTimeout(() => {
                this.thrower_second()
            }, 1000);
        }, 1000)
    },
    methods: {
        changeChart(chng) {
            if (chng == 'Month') {
                this.thrower_first
            } else {
                this.change_chart_check = 'Day Checked!'
            }
        },
        re_fetch_first() {
            this.firstData.datasets[0].data = this.get_TREND_CHART.monthly.yield
            this.firstData.datasets[1].data = this.get_TREND_CHART.monthly.energy
        },
        re_fetch_second() {
            this.secondData.datasets[0].data = this.get_TREND_CHART.monthly.yield
            this.secondData.datasets[1].data = this.get_TREND_CHART.monthly.energy
        },
        get_first(call_first) {
            call_first()
            this.chartData = this.firstData
        },
        get_second(call_second) {
            call_second();
            this.chartData = this.secondData
        },
        thrower_first() {
            this.get_first(this.re_fetch_first);
        },
        thrower_second() {
            this.get_second(this.re_fetch_second);
        }
    }
}
</script>

<style lang="scss" scoped>

</style>