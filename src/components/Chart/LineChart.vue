<template>
  <Line id="my-line-chart-id" :data="chartval" :options="options" />
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
} from 'chart.js';
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
  name: 'LineChart',
  components: {
    Line,
  },
  props: [
    'chartval'
  ],
  data() {
    return {
      // data: {
      //   labels: ['12 hr', '11 hr', '10 hr', '9 hr', '8 hr', '7 hr', '6 hr', '5 hr', '4 hr', '3 hr', '2 hr', '1 hr', '12 hr', '11 hr', '10 hr', '9 hr', '8 hr', '7 hr', '6 hr', '5 hr', '4 hr', '3 hr', '2 hr', '1 hr',],
      //   datasets: [
      //     {
      //       label: 'Current',
      //       borderColor: '#00d25b',
      //       backgroundColor: '#00d25b',
      //       data: [66, 61, 54, 69, 53, 61, 54, 67, 69, 61, 63, 51, 64, 57, 59, 61, 64, 57, 59, 61, 67, 43, 70, 50],
      //       lineTension: 0.4,
      //       borderWidth: 2.0,
      //       pointRadius: 0,
      //     }
      //   ],
      // },
      options: {
        responsive: true,
        maintainAspectRatio: false,
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