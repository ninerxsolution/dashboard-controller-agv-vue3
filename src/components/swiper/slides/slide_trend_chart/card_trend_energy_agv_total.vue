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
            <BarChart :barchartData="chartData" />
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
            chartDataOne: {
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
            chartDataTwo: {
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
    created(){
        setInterval(()=>{
            setTimeout(() => {
                this.updateChartOne()
            }, 6000);
            this.updateCharTwo()
        },6000)
    },
    methods:{
        updateChartOne(){
            this.chartDataOne.datasets[0].data = this.barchartData.yield
            this.chartDataOne.datasets[1].data = this.barchartData.energy
            this.chartData = this.chartDataOne
        },
        updateCharTwo(){
            this.chartDataTwo.datasets[0].data = this.barchartData.yield
            this.chartDataTwo.datasets[1].data = this.barchartData.energy
            this.chartData = this.chartDataTwo
        }
    }
}
</script>

<style lang="scss" scoped>

</style>