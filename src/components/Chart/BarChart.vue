<template>
    <Bar id="my-chart-id" :options="chartOptions" :data="chartData" />
</template>
  
<script>
import { Bar } from 'vue-chartjs'
import { Chart as ChartJS, Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale } from 'chart.js'

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
                        data: [40, 20, 30, 61, 34, 59, 23, 61, 24, 47, 39, 51],
                        backgroundColor: 'yellow',
                    },
                    {
                        label: 'Enegy',
                        data: [23, 73, 14, 46, 34, 11, 76, 49, 50, 21, 53, 22],
                        backgroundColor: 'orange',
                    }
                ],
            },
            chartOptions: {
                responsive: true
            }
        }
    }
}
</script>

<style>
#my-chart-id {
    max-height: 70%;
    /* background-color: aqua; */
}
</style>