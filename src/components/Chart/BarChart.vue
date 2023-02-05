<template>
    <Bar id="my-chart-id" :options="chartOptions" :data="chartData" />
</template>
  
<script>
import { Bar } from 'vue-chartjs'
import { Chart as ChartJS, Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale } from 'chart.js'
// import axios from 'axios'
ChartJS.register(Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale)

export default {
    name: 'BarChart',
    components: { Bar },
    data() {
        return {
            chartData: {
                labels: ['Jan', 'Feb', 'Mar', 'Api', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
                datasets: [
                    {
                        label: 'Yield',
                        data: [23, 67, 89, 45, 23, 67, 89, 45, 23, 89, 45, 23],
                        backgroundColor: 'yellow',
                    },
                    {
                        label: 'Enegy',
                        data: [23, 67, 89, 45, 23, 67, 89, 45, 23, 67, 89, 45],
                        backgroundColor: 'orange',
                    }
                ],
            },
            firstData: {
                labels: ['Jan', 'Feb', 'Mar', 'Api', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
                datasets: [
                    {
                        label: 'Yield',
                        data: [23, 67, 89, 45, 23, 67, 89, 45, 23, 89, 45, 23],
                        backgroundColor: 'yellow',
                    },
                    {
                        label: 'Enegy',
                        data: [23, 67, 89, 45, 23, 67, 89, 45, 23, 67, 89, 45],
                        backgroundColor: 'orange',
                    }
                ],
            },
            secondData: {
                labels: ['Jan', 'Feb', 'Mar', 'Api', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
                datasets: [
                    {
                        label: 'Yield',
                        data: [23, 67, 89, 45, 23, 67, 89, 45, 23, 89, 45, 23],
                        backgroundColor: 'yellow',
                    },
                    {
                        label: 'Enegy',
                        data: [23, 67, 89, 45, 23, 67, 89, 45, 23, 67, 89, 45],
                        backgroundColor: 'orange',
                    }
                ],
            },
            chartOptions: {
                responsive: true
            },
            getJson: '',
            getYield: '',
            getEnergy: '',
        }
    },
    props: {
        get_lists: {
            type: Object,
            required: true
        }
    },
        // created() {
    //     this.fetchData();
    //     setInterval(() => {
    //         this.fetchData()
    //     },1000)
        
    //     setInterval(()=>{
    //         this.thrower_first()
    //         setTimeout(() => {
    //             this.thrower_second()
    //         }, 1000);
    //     },1000)
    // },
    // methods: {
    //     async fetchData() {
    //         try {
    //             const response = await axios.get('https://se-sskru.com/ev-rail/json/AGV_1/-1')
    //             this.getJson = response.data.graph.monthly
    //         } catch (error) {
    //             console.error(error)
    //         }
    //     },
    //     re_fetch_first(){
    //         this.firstData.datasets[0].data = this.get_lists.yield
    //         this.firstData.datasets[1].data = this.get_lists.energy
    //     },
    //     re_fetch_second(){
    //         this.secondData.datasets[0].data = this.get_lists.yield
    //         this.secondData.datasets[1].data = this.get_lists.energy
    //     },
    //     get_first(call_first){
    //         call_first()
    //         this.chartData = this.firstData
    //     },
    //     get_second(call_second){
    //         call_second();
    //         this.chartData = this.secondData
    //     },
    //     thrower_first(){
    //         this.get_first(this.re_fetch_first);
    //     },
    //     thrower_second(){
    //         this.get_second(this.re_fetch_second);
    //     }
    // }
}
</script>

<style>
@media (min-width: 1000px) {
    #my-chart-id {
        max-height: 140px;
    }
}

@media (min-width: 1100px) {
    #my-chart-id {
        max-height: 160px;
    }
}

@media (min-width: 1300px) {
    #my-chart-id {
        max-height: 185px;
    }
}

@media (min-width: 1600px) {
    #my-chart-id {
        max-height: 200px;
    }
}
</style>