<template>
  
  <div>
    <span>{{currentTime}}</span>
  </div>
</template>

<script>
export default {
  data(){
    return{
     currentTime: '',
     timer:''
    }
  },
  created(){
    var weekday = '星期' + '日一二三四五六'.charAt(new Date().getDay());
    this.weekday = weekday;
  },
  mounted(){
     var _this = this; //声明一个变量指向Vue实例this，保证作用域一致
        this.timer = setInterval(function() {
            _this.currentTime = //修改数据date
                new Date().getFullYear() +
                '年' +
                (new Date().getMonth() + 1) +
                '月' +
                new Date().getDate() +
                '日  ' +
                _this.weekday +
                new Date().getHours() +
                `:${new Date().getMinutes() >= 10 ? '' : '0'}` +
                new Date().getMinutes() +
                ':' +
                `${new Date().getSeconds() >= 10 ? '' : '0'}` +
                new Date().getSeconds();
        }, 100);
  }
  

}
</script>

<style lang="less" scoped>

</style>