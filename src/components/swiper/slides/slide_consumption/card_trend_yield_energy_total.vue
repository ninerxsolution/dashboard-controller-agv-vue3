<template>
    <div class="card">
        <!-- {{ get_TREND_CHART.monthly }} -->
        <div class="card-body">
            <div class="col-12 d-flex justify-content-between">
                <h5 class="d-flex">
                    TREND YIELD AND ENEGY TOTAL
                </h5>
                {{ num }} {{ Hithere }}
                <div class="btn-group d-flex" role="group" aria-label="Basic example">
                    <!-- <button type="button" class="btn btn-outline-secondary">
                        Year 
                    </button> --> 
                    {{ Choose }}
                    <button type="button" class="btn btn-outline-secondary" @click="updateChart('Month')">
                        Month
                    </button>
                    <button type="button" class="btn btn-outline-secondary" @click="updateChart('Day')">
                        Day
                    </button>
                    {{ change_chart_check }}
                </div>
            </div>
            <BarChart :barchartData="chartData" />
            {{ GetChange[0] }}
        </div>
    </div>
</template>

<script>
import BarChart from '@/components/Chart/BarChart_TrendEnergy.vue';
export default {
    components: {
        BarChart,
    },
    data() {
        return {
            change_chart_check: 'Day',
            GetChange: 'Default',
            Choose: 'Default',
            num:0,
            Hithere:'',
            chartData: {
                labels: ['Jan', 'Feb', 'Mar', 'Api', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec', 'Jan', 'Feb', 'Mar', 'Api', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec',],
                datasets: [
                    {
                        label: 'Yield',
                        data: [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
                        backgroundColor: 'yellow',
                    },
                    {
                        label: 'Enegy',
                        data: [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
                        backgroundColor: 'orange',
                    }
                ],
            },
            dayDataOne: {
                labels: ['1', '2', '3', '4', '5', '6', '7', '8', '9', '10', '11', '12', '13', '14', '15', '16', '17', '18', '19', '20', '21', '22', '23', '24', '25', '26', '27', '28', '29', '30'],
                datasets: [
                    {
                        label: 'Yield',
                        data: [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
                        backgroundColor: 'yellow',
                    },
                    {
                        label: 'Enegy',
                        data: [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
                        backgroundColor: 'orange',
                    }
                ],
            },
            dayDataTwo: {
                labels: ['1', '2', '3', '4', '5', '6', '7', '8', '9', '10', '11', '12', '13', '14', '15', '16', '17', '18', '19', '20', '21', '22', '23', '24', '25', '26', '27', '28', '29', '30'],
                datasets: [
                    {
                        label: 'Yield',
                        data: [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
                        backgroundColor: 'yellow',
                    },
                    {
                        label: 'Enegy',
                        data: [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
                        backgroundColor: 'orange',
                    }
                ],
            },
            monthDataOne: {
                labels: ['Jan', 'Feb', 'Mar', 'Api', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec',],
                datasets: [
                    {
                        label: 'Yield',
                        data: [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
                        backgroundColor: 'yellow',
                    },
                    {
                        label: 'Enegy',
                        data: [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
                        backgroundColor: 'orange',
                    }
                ],
            },
            monthDataTwo: {
                labels: ['Jan', 'Feb', 'Mar', 'Api', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec',],
                datasets: [
                    {
                        label: 'Yield',
                        data: [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
                        backgroundColor: 'yellow',
                    },
                    {
                        label: 'Enegy',
                        data: [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
                        backgroundColor: 'orange',
                    }
                ],
            },
        }
    },
    props: {
        get_TREND_CHART: {
            type: String,
        }
    },
    created() {
        this.Hithere = "Hi there!"
        // this.dailySet()
        // this.monthlySet()
        setInterval(() => {
            setTimeout(() => {
            this.num+=1
                if (this.Choose == 1) {
                    this.updateChartOne(this.dailySet())
                    this.Hithere = this.Choose
                } else if (this.Choose == 2) {
                    this.updateChartOne(this.monthlySet())
                    this.Hithere = this.Choose
                }
            }, 1000);
            // this.updateChartTwo()
            this.num+=1
            if (this.Choose == 1) {
                this.updateChartOne(this.dailySet())
            } else if (this.Choose == 2) {
                this.updateChartOne(this.monthlySet())
            }
        }, 1000)
    },
    methods: {
        updateChart(choose) {
            if (choose == 'Month') {
                this.GetChange = this.dailySet()
                this.change_chart_check = choose
                this.Choose = 2
            } else if (choose == 'Day') {
                this.change_chart_check = choose
                this.GetChange = this.monthlySet()
                this.Choose = 1
            }
        },
        dailySet() {
            this.dayDataOne.datasets[0].data = this.get_TREND_CHART.daily.yield
            this.dayDataOne.datasets[1].data = this.get_TREND_CHART.daily.energy
            // this.dayDataTwo.datasets[0].data = this.get_TREND_CHART.daily.yield
            // this.dayDataTwo.datasets[1].data = this.get_TREND_CHART.daily.energy
            return [this.dayDataOne]

        },
        monthlySet() {
            this.monthDataOne.datasets[0].data = this.get_TREND_CHART.monthly.yield
            this.monthDataOne.datasets[1].data = this.get_TREND_CHART.monthly.energy
            // this.monthDataTwo.datasets[0].data = this.get_TREND_CHART.monthly.yield
            // this.monthDataTwo.datasets[1].data = this.get_TREND_CHART.monthly.energy
            return [this.monthDataOne]
        },
        updateChartOne(dataSet) {
            dataSet
            this.chartData = this.dataSet
        },
        updateChartTwo(dataSet) {
            dataSet
            this.chartData = this.dataSet
        }
    }
}
</script>

<style lang="scss" scoped>

</style>