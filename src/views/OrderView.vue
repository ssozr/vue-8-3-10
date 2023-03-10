<style>
.order-progress {
  height: 90px;
}
.order-progress li {
  list-style-type: none;
  float:left;
  width: 33.3%;
  height: 50px;
  position:relative;
  text-align:center;
}

.order-progress li:before {
  content:"";
  counter-increment: step;
  width:30px;
  height:30px;
  line-height:30px;
  border:1px solid #ddd;
  display:block;
  text-align:center;
  margin:0 auto 10px auto;
  border-radius:50%;
  background-color:#fff;
}

.order-progress li:after {
  content:"";
  border:1px solid #ddd;
  position: absolute;
  width:100%;
  height:1px;
  background-color:#ddd;
  top:15px;
  left:-50%;
  z-index:-1;
}

.order-progress li:first-child:after{
  content:none;
}

.order-progress li.active {
  color:#F79E1B;
}

.order-progress li.active:before {
  border-color:#F79E1B;
}

.order-progress li.active:after {
  background-color:#F79E1B;
}

</style>

<template>
  <div class="container-fuli">
    <div class="row">
      <ul class="order-progress pt-4">
        <li class="active">填寫資料</li>
        <li :class="{active:num >= 2}">付款</li>
        <li :class="{active:num >= 3}">完成訂單</li>
      </ul>
    </div>
    <div class="row">
      123
    </div>
  </div>
</template>

<script>
export default {
    data () {
    return {
      num:1,
      text:"123"
    }
  },
  methods: {
    nextBtn(){
      this.num ++
    },
    preBtn(){
      this.num--
    }
  }
}
</script>
