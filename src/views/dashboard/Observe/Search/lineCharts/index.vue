<template>
  <div>
      <div class="header">
          <span class="search-header">搜索用户数</span>
          <svg t="1651023076924" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="2055" width="26" height="26"><path d="M512 958.016C266.08 958.016 65.984 757.952 65.984 512 65.984 266.08 266.08 65.984 512 65.984c245.952 0 446.016 200.064 446.016 446.016C958.016 757.952 757.952 958.016 512 958.016zM512 129.984C301.344 129.984 129.984 301.344 129.984 512c0 210.624 171.36 382.016 382.016 382.016 210.624 0 382.016-171.36 382.016-382.016C894.016 301.344 722.624 129.984 512 129.984z" p-id="2056"></path><path d="M512 304m-48 0a1.5 1.5 0 1 0 96 0 1.5 1.5 0 1 0-96 0Z" p-id="2057"></path><path d="M512 768c-17.664 0-32-14.304-32-32l0-288c0-17.664 14.336-32 32-32s32 14.336 32 32l0 288C544 753.696 529.664 768 512 768z" p-id="2058"></path></svg>
      </div>
      <div class="main">
          <span class="main-title">12321</span>
          <span class="main-content">17.1</span>
          <span><svg t="1651024648152" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="2042" width="16" height="16"><path d="M858.9 689L530.5 308.2c-9.4-10.9-27.5-10.9-37 0L165.1 689c-12.2 14.2-1.2 35 18.5 35h656.8c19.7 0 30.7-20.8 18.5-35z" p-id="2043" fill="#1afa29"></path></svg></span>
          <span><svg t="1651024801661" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="2971" width="16" height="16"><path d="M840.4 300H183.6c-19.7 0-30.7 20.8-18.5 35l328.4 380.8c9.4 10.9 27.5 10.9 37 0L858.9 335c12.2-14.2 1.2-35-18.5-35z" p-id="2972" fill="#d81e06"></path></svg></span>
      </div>
      <div class="footer">
          <div class="charts" ref="charts"></div>
      </div>
  </div>
</template>

<script>
import * as echarts from 'echarts';
export default {
    name:'',
    mounted() {
        //初始化echarts实例
        let lineCharts = echarts.init(this.$refs.charts);
        //配置数据
        lineCharts.setOption({
            xAxis:{
                //隐藏x轴
                show:false,
                type:'category'
            },
            yAxis:{
                show:false,
            },
            //系列
            series:[
                {
                    type:'line',
                    data:[10,7,33,12,48,9,29,10,44],
                    smooth:true,
                    //拐点样式的设置
                    itemStyle:{
                        opacity:0
                    },
                    //线条的样式
                    lineStyle:{
                        color:"blue"
                    },
                    //填充颜色设置
                    areaStyle:{
                        color:{
                            type:"linear",
                            x:0,
                            y:0,
                            x2:0,
                            y2:1,
                            colorStops:[
                                {
                                    offset:0,
                                    color:"blue", //0%处的颜色
                                },
                                {
                                    offset:1,
                                    color:"#fff", //100%处的颜色
                                },
                            ],
                            globel:false, //缺省为false
                        }
                    }
                },
            ],
            //布局调试
            grid:{
                left:0,
                top:0,
                right:0,
                bottom:0
            }
        })
    },
}
</script>

<style>
.header {
    display: flex;
    /* 垂直居中 */
    align-items: center;    
}
.search-header{
    margin-right: 20px;
}
.main {
    margin: 10px 0;
}
.main-title{
    margin-right: 30px;
}
.main-content{
    margin-right: 10px;
}
.charts{
    width: 100%;
    height: 50px;
}
</style>