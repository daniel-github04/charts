<script>
import HelloWorld from './components/HelloWorld.vue'
import * as echarts from 'echarts';
import { onMounted, ref } from 'vue'

export default {
  setup() {
    // Create the echarts instance
    const chartContainer = ref(null)

    onMounted(() => {
      // Draw the chart
      echarts.init(chartContainer.value).setOption({
        title: {
          text: 'ECharts Getting Started Example'
        },
        tooltip: {},
        xAxis: {
          data: ['shirt', 'cardigan', 'chiffon', 'pants', 'heels', 'socks']
        },
        yAxis: {},
        series: [
          {
            name: 'sales',
            type: 'bar',
            data: [5, 20, 36, 10, 10, 20]
          }
        ]
      });
    })

    return {
      chartContainer
    }
    
  }
}
</script>

<template>
  <!-- <div>
    <a href="https://vite.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
  </div>
  <HelloWorld msg="Vite + Vue" /> -->
  <div class="d-flex flex-column align-center justify-center flex-1-1">
    <div ref="chartContainer" class="chart-container"></div>
  </div>
  <h1>Hola mundo</h1>
</template>

<style scoped>

.chart-container {
  width: 600px;
  height: 400px;
}

.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
