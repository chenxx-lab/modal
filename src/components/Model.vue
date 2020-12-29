<!-- 模态弹窗 -->
<template>
    <!--<div class="self-modal" v-show='showModal'  @click="cancelClick" v-bind:style="styleObj" @touchmove.stop.prevent>
      <!-- 自定义内容 -->
      <!--<slot></slot>
    </div>-->
    <div class="selfmodal" v-show='showModal' v-bind:style="styleObj" @click.prevent.stop>
    	<!-- 自定义内容 -->
    	<div class="modal">
    	<slot><div class="title">标题</div></slot>
    	<slot><div class="content">内容区</div></slot>
    	<div class="btn">
    		<button class="btn1" @click="cancelClick">取消</button>
    		<button class="btn2" @click="sureClick">确定</button>
    	</div>
    	</div>
    </div>
</template>
<script>
export default {
  name: 'selfModal',
  data () {
    return {
      showModal: false
    }
  },
  props: {
    styleObj: { // 用于承接样式类
      type: Object,
      default: function () {
        return {
          position: 'fixed',
          bottom: 0,
          top: 0,
          left: 0,
          width: '100%',
          background: 'rgba(113,111,111,0.5)'
        }
      }
    }
  },
  methods: {
    // 确定
    sureClick () {
      this.showModal = true
      return new Promise(function (resolve) {
        resolve('sure')
      }, function (reject) {})
    },
    // 取消
    cancelClick () {
      this.showModal = false
      return new Promise(function (resolve) {
        resolve('cancel')
      }, function (reject) {})
    }
  }
}
</script>
<style>
.selfmodal{
  z-index: -1;
  background: 'rgba(113,111,111,0.5)';
  
  }
  .modal{
  	background: cornflowerblue;
  	align-content: center;
  	margin-top: 12%;
  	margin-left: 30%;
  	width: 500px;
  	height: 300px;
  }
  .title{
  	padding-left: 45%;
  	padding-top: 5%;
  }
  .content{
  	padding-left: 43%;
  	padding-top: 15%;
  }
  .btn1{
  	margin-top: 100px;
  	margin-left: 100px;
  	background: green;
  }
  .btn2{
  	margin-top: 100px;
  	margin-left: 200px;
  	background: green;
  }
</style>