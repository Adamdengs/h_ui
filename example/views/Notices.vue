<template>
	<div>	
	  <h1>Notice 通知提醒</h1>	
	  <h1>基础用法 </h1>	
		<h-button type="primary" @click="open(false)">打开提醒</h-button>
    <h-button @click="open(true)">打开提醒（仅标题）</h-button>
  	<h1>提醒类型</h1>
  	<h2>带描述信息</h2>
    <h-button @click="info(false)">消息</h-button>
    <h-button @click="success(false)">成功</h-button>
    <h-button @click="warning(false)">警告</h-button>
    <h-button @click="error(false)">错误</h-button>
    <h2>仅标题</h2>
    <h-button @click="info(true)">消息</h-button>
    <h-button @click="success(true)">成功</h-button>
    <h-button @click="warning(true)">警告</h-button>
    <h-button @click="error(true)">错误</h-button>
    <h-button @click="error(true)">错误</h-button>
    <h2>自定义提示存在时间 duration为 0 则不自动关闭</h2>
    <h-button type="primary" @click="time">打开提醒</h-button>
    <h-button type="primary" @click="close">关闭name为key1的notice</h-button>
    <h-button type="primary" @click="destroy">全局销毁</h-button>
	</div>
</template>
<script>	
	export default{
		name:"Notices",
		data(){
			return {}
		},
		methods: {
      open (nodesc) {
        this.$hNotice.open({
          title: '这是通知标题',
          desc: nodesc ? '' : '这里是通知描述这里,是通知描述这里是通知描述这里,是通知描述这里,是通知描述这里是通知描述这里是通知描述',
        });
      },
      info (nodesc) {
        this.$hNotice.info({
          title: '这是通知标题',
          desc: nodesc ? '' : '这里是通知描述这里,是通知描述这里是通知描述这里,是通知描述这里,是通知描述这里是通知描述这里是通知描述',
          duration: 0
        });
      },
      success (nodesc) {
        this.$hNotice.success({
          title: '这是通知标题',
          desc: nodesc ? '' : '这里是通知描述这里,是通知描述这里是通知描述这里,是通知描述这里,是通知描述这里是通知描述这里是通知描述'
        });
      },
      warning (nodesc) {
        this.$hNotice.warning({
          title: '这是通知标题',
          desc: nodesc ? '' : '这里是通知描述这里,是通知描述这里是通知描述这里,是通知描述这里,是通知描述这里是通知描述这里是通知描述'
        });
      },
      error (nodesc) {
        this.$hNotice.error({
          title: '这是通知标题',
          desc: nodesc ? '' : '这里是通知描述这里,是通知描述这里是通知描述这里,是通知描述这里,是通知描述这里是通知描述这里是通知描述'
        });
      },
      time () {
        this.$hNotice.open({
          title: '这是通知标题',
          desc: '这条通知不会自动关闭，需要点击关闭按钮才可以关闭。',
          duration: 0
        });
      },
      close(){
        this.$hNotice.close('key1')
      },
      destroy(){
        this.$hNotice.destroy()
      }

    },
    mounted () {
      this.$hNotice.config({
          top: 200,
          duration: 3
      });
    }
	}
</script>
<style>
	
</style>