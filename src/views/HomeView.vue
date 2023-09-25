<template>
  <div class="chart">
    <div class="main">
      <p class="p_1">Total Statistics</p>
      <div class="main_box">
        <canvas id="myChart" height="100"></canvas>
      </div>
    </div>
    <div class="chart_right">
      <p>Popular courses</p>
      <div class="box">
        <p class="p_2">Courses in Progress</p>
        <div class="box_i">
          <h2>32</h2>
          <i class="fa-solid fa-square-poll-vertical"></i>
        </div>
      </div>
      <div class="box">
        <p class="p_2">Complatet Courses</p>
        <div class="box_i">
          <h2>14</h2>
          <i class="fa-regular fa-circle-check"></i>
        </div>
      </div>
      <div class="box">
        <p class="p_2">Watching Time</p>
        <div class="box_i">
          <h2>214h</h2>
          <i class="fa-solid fa-video"></i>
        </div>
      </div>
      <div class="box">
        <p class="p_2">Earning Points</p>
        <div class="box_i">
          <h2>8</h2>
          <i class="fa-regular fa-circle-up"></i>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import {onMounted}from "vue"
import Chart from 'chart.js/auto'

const data = [
    {year:2010,count:10},
    {year:2011,count:20},
    {year:2012,count:15},
    {year:2013,count:25},
    {year:2014,count:12},
    {year:2015,count:30},
    {year:2016,count:28},
]

onMounted(()=>{
    new Chart(
        document.getElementById('myChart'),
        {
            type:"line",
            data:{
                labels:data.map(row=>row.year),
                datasets:[
                    {
                        label:"Acquistions by year",
                        data:data.map(row=>row.count)
                    }
                ]
            }
        }
    )
})

</script>


<style lang="scss" scoped>
.chart{
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: row;
  background-color: rgb(219, 214, 214);
}

.main{
  width: 70%;
  height: 350px;
  background-color: rgb(219, 214, 214);
  border-radius: 9px;
  display: flex;
  flex-direction: column;
  margin: 20px;
  gap: 10px;
  align-items: flex-start;
}
.main_box{
  width: 100%;
  background-color: white;
  border-radius: 9px;
}



.chart_right{
  width: 30%;
  display: flex;
  flex-direction: column;
  margin: 20px;
  gap: 10px;
  align-items: flex-start;
}

.box{
  width: 100%;
  display: flex;
  flex-direction: column;
  background-color:rgb(255, 255, 255);
  border-radius: 9px;
  align-items: flex-start;
  &:hover {
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  }
}

.p_2{
  margin-left: 10px;
}

.box_i{
  width: 100%;
  display: flex;
  justify-content: space-between;
  margin-left: 10px;
  .fa-solid{
    margin-right: 20px;
    font-size: 30px;
  }
  .fa-regular{
    margin-right: 20px;
    font-size: 30px;
  }
}

</style>
