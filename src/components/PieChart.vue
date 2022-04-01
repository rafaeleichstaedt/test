<template>
    <JSCharting :options="chartOptions" class="columnChart"></JSCharting>
</template>

<script>
import JSCharting from 'jscharting-vue';

export default {
   name: 'columnChart',
   components: {
      JSCharting
   },
   props:{
       points:{default:null, type:Array},
       name:{default:null,type:String}
   },
   data() {
      return {
         chartOptions: {
            defaultSeries: { type: 'pie', pointSelection: true },
            defaultPoint_label_text: '%PercentOfTotal%',
            legend: {
                template: '{%percentOfTotal:n1}% %icon %name',
                position: 'inside left bottom'
            },
            series: [
               {
                name:this.name,
                points: this.points
               }
            ]
         }
      }
   },
   
}
</script>

<style>
.columnChart {
    height: 300px;
}
</style>