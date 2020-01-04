<template>
	<view class="content">
		<view class="title">{{title}}</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: ''
			}
		},
		onLoad:function(e){
			//console.log(e);
			var newsid=e.newsid;
			console.log(newsid);
			uni.request({
				url: 'https://unidemo.dcloud.net.cn/api/news/36kr/'+newsid,
				method: 'GET',
				data: {},
				success: res => {
					console.log(res);
					this.title = res.data.title;
				},
				fail: () => {},
				complete: () => {}
			});
			
		},
		
	}
</script>

<style>
.content{padding: 10upx 2%; width: 96%; flex-wrap: wrap; } 
.title{line-height: 2em; font-weight: 800; font-size: 30upx;}
</style>
