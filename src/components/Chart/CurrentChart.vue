<template>
    <Bar id="trend-chart" :options="chartOptions" :data="chartData" />
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
                labels: ['12 hr', '11 hr', '10 hr','9 hr', '8 hr', '7 hr','6 hr', '5 hr', '4 hr','3 hr', '2 hr', '1 hr','12 hr', '11 hr', '10 hr','9 hr', '8 hr', '7 hr','6 hr', '5 hr', '4 hr','3 hr', '2 hr', '1 hr',],
                datasets: [
                    {
                        label: 'Current',
                        data: [67, 60, 66, 61, 54, 69, 53, 61, 54, 67, 69, 61, 63, 51, 64, 57, 59, 61, 64, 57, 59, 61,67,43],
                        backgroundColor: 'green',
                    },
                    // {
                    //     label: 'Enegy',
                    //     data: [70, 73, 14, 46, 34, 11, 76, 49, 50, 21, 53, 22, 14, 46, 34, 11, 23, 11],
                    //     backgroundColor: 'white',
                    // }
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
    #trend-chart {
        max-height: 90px;
    }
}
@media (min-width: 1100px) {
    #trend-chart {
        max-height: 100px;
    }
}
@media (min-width: 1300px) {
    #trend-chart {
        max-height: 110px;
    }
}
@media (min-width: 1600px) {
    #trend-chart {
        max-height: 110px;
    }
}
</style>