<template>
  <div class="bg-white rounded-lg">
    <apex-chart
      type="area"
      :options="chartOptions"
      :series="series"
    ></apex-chart>
  </div>
</template>

<script lang="ts">
import { defineComponent, onMounted } from "vue";
import moment from 'moment'
import axios from 'axios'
import VueApexCharts from "vue3-apexcharts";

let interval: number;

export default defineComponent({
    data: function() {
        return {
            chartOptions: {
                chart: {
                    type: 'area',
                    stacked: false,
                    height: 350,
                    zoom: {
                        enabled: false
                    },
                    toolbar: {
                        show: false
                    }
                },
                colors: ['#ea580c'],
                stroke: {
                    width: 1
                },
                dataLabels: {
                    enabled: false
                },
                markers: {
                    size: 0,
                },
                fill: {
                    type: 'gradient',
                    gradient: {
                        shadeIntensity: 1,
                        inverseColors: false,
                        opacityFrom: 0,
                        opacityTo: 0,
                        stops: [20, 100, 100, 100]
                    },
                },
                yaxis: {
                    show: false
                },
                xaxis: {
                    type: 'datetime',
                },
                tooltip: {
                    shared: true
                },
                grid: {
                    yaxis: {
                        lines: {
                            show: false
                        }
                    }
                }
            },
            series: [
                {
                name: "series-1",
                data: [{
                        x: new Date('2018-02-11').getTime(),
                        y: 76
                    }, {
                        x: new Date('2018-02-12').getTime(),
                        y: 90
                    }],
                },
            ]
        };
    },
    components: {
        apexChart: VueApexCharts
    },
    methods: {
        async getData() {
            axios.defaults.headers.get['Content-Type'] ='application/json;charset=utf-8';
            axios.defaults.headers.get['Access-Control-Allow-Origin'] = '*';
            const res = axios.get('https://www.coingecko.com/price_charts/1/usd/24_hours.json');
            console.log(res);
        }
    },
    mounted() {
        interval = setTimeout(() => {
            this.getData();
        }, 1000)
    },
    unmounted() {

    }
})
</script>
