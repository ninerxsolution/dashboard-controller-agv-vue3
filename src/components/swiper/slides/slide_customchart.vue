<template>
    <div>
        {{  }} {{ this.data.labels }} {{ getData }}
        <Line :options="options" :type="type" :data="data" />
        {{ this.data.datasets[0].data }}
    </div>
</template>

<script>
import { Line } from 'vue-chartjs'
import axios from 'axios'

export default {
    components: {
        Line
    },
    data() {
        return {
            jsonData: '',
            getData: this.jsonData,
            type: 'line',
            options: {
                scales: {
                    yAxes: [
                        {
                            ticks: {
                                beginAtZero: true
                            }
                        }
                    ]
                }
            },
            data: {
                labels: [],
                datasets: [
                    {
                        label: 'Data One',
                        backgroundColor: '#f87979',
                        data: []
                    }
                ]
            }
        }
    },
    mounted() {
        axios
            .get('https://se-sskru.com/ev-rail/json/AGV_1/-1')
            .then(response => {
                this.jsonData = response.data
                this.data.labels = Object.keys(response.data.graph.monthly)
                this.data.datasets[0].data = response.data.graph.monthly.yield
                this.renderChart(this.data, this.options)
            })
            .catch(error => {
                console.error(error)
            })
    }
}
</script>

