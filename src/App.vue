<template>
  <div id="app">
    <Bar
      id="my-chart-id"
      :options="mixedOptions"
      :data="mixedData"
    />
  </div>
</template>

<script lang="ts">
import { Bar, Line } from 'vue-chartjs';
import { Chart as ChartJS, Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale, PointElement, LineElement, Filler } from 'chart.js';

ChartJS.register(
  CategoryScale,
  LinearScale,
  BarElement,
  PointElement,
  LineElement,
  Title,
  Tooltip,
  Legend,
  Filler
)

export default {
  name: 'Test',
  components: { Bar, Line },
  data() {
    return {
      mixedData: {
        datasets: [
          {
            type: 'line',
            label: 'Revenue',
            borderColor: '#2C69FF',
            data: [12, 20, 50],
            fill: 'origin',
            backgroundColor: 'rgba(44,105,255,0.1)',
            pointRadius: 5,
            borderWidth: 2,
            pointBorderColor: '#2C69FF',
            pointBackgroundColor: '#fff'
          },
          {
            type: 'line',
            label: 'Quota',
            borderColor: '#000',
            data: [45, 45, 45],
            pointRadius: 5,
            borderWidth: 2,
            backgroundColor: '#fff',
            pointBorderColor: '#000',
            pointBackgroundColor: '#fff'
          },
        ],
        labels: [ 'January', 'February', 'March' ],
      },
      mixedOptions: {
        responsive: true,
        scales: {
          x: {
            offset: false,
            grid: {
              display: false
            },
            ticks: { padding: 20 },
          },
          y: {
            border: { display: false },
            ticks: { padding: 20 },
          }
        }
      },
    }
  }
}
</script>
