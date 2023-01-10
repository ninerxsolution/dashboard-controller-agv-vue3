<template>
    <Bar id="my-chart-id" :options="chartOptions" :data="chartData" />
</template>
  
<script>
import { Bar } from 'vue-chartjs'
import { Chart as ChartJS, Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale } from 'chart.js'

ChartJS.register(Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale)

export default {
    name: 'CustomChart',
    components: { Bar },
    data() {
        return {
            chartData: {
                labels: ['Jan', 'Feb', 'Mar', 'Api', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec', 'Feb', 'Mar', 'Api', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
                datasets: [
                    {
                        label: 'Yield',
                        data: [40, 20, 30, 61, 34, 59, 23, 61, 24, 47, 39, 51, 20, 30, 61, 34, 59, 23, 61, 24, 47, 39, 51],
                        backgroundColor: 'yellow',
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