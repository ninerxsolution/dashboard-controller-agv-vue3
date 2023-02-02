

<!-- <template>
  <div>
    <line-chart :options="options" :data="data"></line-chart>
  </div>
</template>

<script>
import { Line } from 'vue-chartjs'

export default {
  components: {
    LineChart: Line
  },
  data () {
    return {
      options: {
        scales: {
          yAxes: [{
            gridLines: {
              display: false,
              drawBorder: false
            },
            ticks: {
              display: false
            }
          }],
          xAxes: [{
            gridLines: {
              display: false,
              drawBorder: false
            },
            ticks: {
              display: false
            }
          }]
        },
        legend: {
          display: false
        },
        responsive: true,
        maintainAspectRatio: false
      },
      data: {
        labels: ['A', 'B', 'C', 'D', 'E', 'F'],
        datasets: [
          {
            label: 'Data One',
            backgroundColor: 'rgba(220,53,69,0.5)',
            data: [40, 39, 10, 40, 39, 80],
            fill: true,

          }
        ]
      }
    }
  }
}
</script> -->


<template>
  <Line id="my-line-chart-id" :data="data" :options="options" :chartData="chartData"
    :chartOptions="chartOptions"
    :chartId="chartId"
    :width="width"
    :height="height"
    :cssClasses="cssClasses"
    :styles="styles"
    :plugins="plugins"/>
</template>
  
<script type="ts">
// import { USERWHITESPACABLE_TYPES } from '@babel/types';
import {
  Chart as ChartJS,
  CategoryScale,
  LinearScale,
  PointElement,
  LineElement,
  Title,
  Tooltip,
  Legend,
  // Plugin,
  // Filler,
} from 'chart.js';
ChartJS.register(Title, Tooltip, Legend, LineElement, LinearScale, CategoryScale, PointElement)
import { Line } from 'vue-chartjs';
// import { util } from 'webpack';

ChartJS.register(
  CategoryScale,
  LinearScale,
  PointElement,
  LineElement,
  Title,
  Tooltip,
  Legend
);

export default {
  extends: Line,

  name: 'LIneChart',
  components: {
    Line,
  },
  props: {
    chartId: {
      type: String,
      default: 'line-chart'
    },
    width: {
      type: Number,
      default: 400
    },
    height: {
      type: Number,
      default: 160
    },
    cssClasses: {
      default: '',
      type: String
    },
    styles: {
      type: Object,
      default: () => {}
    },
    plugins: {
      type: Array,
      default: () => []
    }
  },
  data() {
    return {
      gradient: null,
      gradient2: null,
      data: {
        labels: ['12 hr', '11 hr', '10 hr', '9 hr', '8 hr', '7 hr', '6 hr', '5 hr', '4 hr', '3 hr', '2 hr', '1 hr', '12 hr', '11 hr', '10 hr', '9 hr', '8 hr', '7 hr', '6 hr', '5 hr', '4 hr', '3 hr', '2 hr', '1 hr',],
        datasets: [
          {
            label: 'Speed',
            borderColor: '#0090e7',
            backgroundColor: '#0090e7',
            data: [67, 60, 66, 61, 54, 69, 53, 61, 54, 67, 69, 61, 63, 51, 64, 57, 59, 61, 64, 57, 59, 61, 67, 43],
            lineTension: 0.4,
            borderWidth: 2.0,
            pointRadius: 1,
            // pointBackgroundColor: 'white',
            fill: true
          }
        ],
      },
      options: {
        responsive: true,
        maintainAspectRatio: false,
        scales: {
          yAxes: [{
            ticks: {
              beginAtZero: true
            }
          }]
        },
        legend: {
          display: false
        }
      },
      chartOptions: {
        responsive: true,
        plugins: {
          legend: {
            display: false
          }
        }
      }
    }
  },
};
</script>

<style scope>
@media (min-width: 438px) {
  #my-line-chart-id {
    max-height: 120px;
  }
}

@media (min-width: 768px) {
  #my-line-chart-id {
    max-height: 150px;
  }
}

@media (min-width: 1000px) {
  #my-line-chart-id {
    max-height: 140px;
  }
}

@media (min-width: 1100px) {
  #my-line-chart-id {
    max-height: 160px;
  }
}

@media (min-width: 1300px) {
  #my-line-chart-id {
    max-height: 185px;
  }
}

@media (min-width: 1600px) {
  #my-line-chart-id {
    max-height: 200px;
  }
}
</style>