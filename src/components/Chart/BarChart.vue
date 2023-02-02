<template>
    <!-- <div v-if="checkValid"> -->
    <Bar id="my-chart-id" :options="chartOptions" :data="chartData" />
    <!-- </div> -->
    AA {{ typeof get_lists }} is type of {{ get_lists }} AA
</template>
  
<script>
import { Bar } from 'vue-chartjs'
import { Chart as ChartJS, Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale } from 'chart.js'

ChartJS.register(Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale)

export default {
    name: 'BarChart',
    components: { Bar },
    computed: {
        checkValid() {
            return this.get_lists && this.get_lists.yield;
        }
    },
    data() {
        return {
            chartData: {
                labels: ['Jan', 'Feb', 'Mar', 'Api', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
                datasets: [
                    {
                        label: 'Yield',
                        data: [10000, 10000, 10000, 10000, 10000, 10000, 2, 4, 5, 4, 3, 2],
                        backgroundColor: 'yellow',
                    },
                    {
                        label: 'Enegy',
                        data: [10000, 2, 3, 5, 4, 3, 2, 4, 5, 4, 3, 2],
                        backgroundColor: 'orange',
                    }
                ],

            },
        }
    },
    watch: {
        data() {
        // energyData: this.get_lists,
            // yieldData: this.get_lists,
            // get_throw: Object.values(this.get_lists),
            this.chartData.datasets[0].data = this.get_lists.yield;
        //     chartOptions: {
        //     responsive: true
        // },
        }

    },
    // mounted() {
    //     this.chartData.datasets = this.chartData.rawData.map(item => ({
    //     label: item.label,
    //     data: item.data.yield,
    //     backgroundColor: item.backgroundColor
    //     }))
    //  },
    props: {
        get_lists: {
            type: Object,
            required: true
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