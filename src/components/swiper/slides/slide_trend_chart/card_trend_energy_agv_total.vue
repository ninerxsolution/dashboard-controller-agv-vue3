<template>
    <div class="card">
        <div class="tranbackground">
        <span></span>
        <span></span>
        <span></span>
        <span></span>
    </div>
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
            <div class="col-12">
                <BarChart :barchartData="chartData" />
            </div>
            <div class="col-12 d-flex justify-content-end" role="group" aria-label="Basic example">
                <div class="btn-group">
                    <button type="button" class="btn btn-outline-secondary" @click="updateChart('Month')">
                        Month
                    </button>
                    <button type="button" class="btn btn-outline-secondary" @click="updateChart('Day')">
                        Day
                    </button>
                </div>
            </div>
            <!-- <span>{{ barchartData }}</span> -->
        </div>
    </div>
</template>

<script>
import BarChart from '@/components/Chart/BarChart_TrendEnergy.vue';

export default {
    components: {
        BarChart,
    },
    props:['barchartData'],
    data(){
        return{
            ToSwitch: 'Day',
            chartData: {
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
                        backgroundColor: 'white',
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
                        backgroundColor: 'white',
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
                        backgroundColor: 'white',
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
                        backgroundColor: 'white',
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
                        backgroundColor: 'white',
                    }
                ],
            },
        }
    },
    created() {
        setInterval(() => {
            setTimeout(() => {
                this.updateChartOne(this.ToSwitch)
            }, 2500);
            this.updateChartTwo(this.ToSwitch)
        }, 2500)
    },
    methods: {
        updateChart(clicked) {
            this.ToSwitch = clicked
            this.updateChartOne(this.ToSwitch)
        },
        updateChartOne(ToSwitch) {
            if (ToSwitch == 'Month') {
                this.monthDataOne.datasets[0].data = this.barchartData.monthly.yield
                this.monthDataOne.datasets[1].data = this.barchartData.monthly.energy
                this.chartData = this.monthDataOne
            } else if (ToSwitch == 'Day') {
                this.dayDataOne.datasets[0].data = this.barchartData.daily.yield
                this.dayDataOne.datasets[1].data = this.barchartData.daily.energy
                this.chartData = this.dayDataOne
            }
        },
        updateChartTwo(ToSwitch) {
            if (ToSwitch == 'Month') {
                this.monthDataTwo.datasets[0].data = this.barchartData.monthly.yield
                this.monthDataTwo.datasets[1].data = this.barchartData.monthly.energy
                this.chartData = this.monthDataTwo

            } else if (ToSwitch == 'Day') {
                this.dayDataTwo.datasets[0].data = this.barchartData.daily.yield
                this.dayDataTwo.datasets[1].data = this.barchartData.daily.energy
                this.chartData = this.dayDataTwo
            }
        },
    }
}
</script>

<style lang="scss" scoped>

</style>