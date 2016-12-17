<template>
	<div>
		<!--
    	作者：ivanyb@qq.com
    	时间：2016-12-06
    	描述：首页轮播图片区域
    	组件：mint-ui
    -->
		<swipe class="my-swipe">
			<swipe-item class="slide1" v-for="item in list">
				<a :href="item.url">
					<img :src="item.img">
				</a>
			</swipe-item>
		</swipe>

		<!--
	作者：ivanyb@qq.com
	时间：2016-12-06
	描述：九宫格区域
-->
		<ul class="mui-table-view mui-grid-view mui-grid-9">
			<li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3">
				<router-link to="/news/imgcontentnews">
					<span class="mui-icon mui-icon-home">
                	
                </span>
					<div class="mui-media-body">新闻资讯</div>
				</router-link>
			</li>
			<li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3">

				<router-link to="/photolist">
					<span class="mui-icon mui-icon-email">
                	<!--<span class="mui-badge">5</span>-->
					</span>
					<div class="mui-media-body">图片分享</div>
				</router-link>
			</li>
			<li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3">

				<router-link to="/search">
					<span class="mui-icon mui-icon-chatbubble"></span>
					<div class="mui-media-body">商品展示</div>
				</router-link>
			</li>
			<li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3">

				<router-link to="/member">
					<span class="mui-icon mui-icon-location"></span>
					<div class="mui-media-body">留言反馈</div>
				</router-link>
			</li>
			<li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3">

				<router-link to="/search">
					<span class="mui-icon mui-icon-search"></span>
					<div class="mui-media-body">搜索资讯</div>
				</router-link>
			</li>
			<li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3">

				<router-link to="/car">
					<span class="mui-icon mui-icon-phone"></span>
					<div class="mui-media-body">联系我们</div>
				</router-link>
			</li>

		</ul>

	</div>
</template>

<script>
	import {Swipe,SwipeItem} from 'mint-ui';
	export default {
		data() {
				return {
					list: [{
						url: 'http://www.itcast.cn/subject/phoneweb/index.html',
						img: 'http://ofv795nmp.bkt.clouddn.com/vuelogobanner1.jpg'
					}, {
						url: 'http://www.itcast.cn/subject/phoneweb/index.html',
						img: 'http://ofv795nmp.bkt.clouddn.com/vuelogobanner2-1.jpg'
					}]
				}
			},
			created() {
				//	 	this.$http.get('http://172.16.0.205:9090/api/getlunbo')
				////	 	this.$http.get('http://czdm.ittun.com/api/getlunbo')
				//	 	.then((res)=>{
				//	 		this.list = res.body;
				//	 	});
			},
			components: {
				Swipe,
				SwipeItem
			}
	}
</script>

<style scoped>
	.my-swipe {
		height: 250px;
		color: #fff;
		font-size: 30px;
		text-align: center;
	}
	
	.slide1 a,
	.slide1 img {
		display: block;
		width: 100%;
		height: 250px;
	}
	
	.mint-swipe-indicator {
		opacity: 1;
		background: rgba(239, 239, 239, 0.8);
	}
	
	.mint-swipe-indicator.is-active {
		opacity: 1;
		background: rgba(250, 250, 10, 0.8)
	}
	
	.mui-icon {
		width: 50px;
		height: 50px;
	}
	
	.mui-icon-home {
		background-image: url(../../../statics/images/menu3.png);
		background-repeat: round;
	}
	
	.mui-icon-email {
		background-image: url(../../../statics/images/menu4.png);
		background-repeat: round;
	}
	
	.mui-icon-chatbubble {
		background-image: url(../../../statics/images/menu5.png);
		background-repeat: round;
	}
	
	.mui-icon-location {
		background-image: url(../../../statics/images/menu6.png);
		background-repeat: round;
	}
	
	.mui-icon-search {
		background-image: url(../../../statics/images/menu9.png);
		background-repeat: round;
	}
	
	.mui-icon-phone {
		background-image: url(../../../statics/images/menu10.png);
		background-repeat: round;
	}
	
	.mui-icon-home:before,
	.mui-icon-email:before,
	.mui-icon-chatbubble:before,
	.mui-icon-location:before,
	.mui-icon-search:before,
	.mui-icon-phone:before {
		content: '';
	}
	
	.mui-grid-view.mui-grid-9 {
		background-color: white;
	}
	
	.mui-grid-view.mui-grid-9 .mui-table-view-cell {
		border: none;
	}
</style>