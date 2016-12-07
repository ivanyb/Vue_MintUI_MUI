<template>
    <div class="news">
    	<header class="mui-bar mui-bar-nav">
			<a href="#/Home" class="mui-action-back mui-icon mui-icon-left-nav mui-pull-left">返回</a>
			<h1 class="mui-title">图文资讯</h1>
		</header>
   		<ul class="mui-table-view">
			<li class="mui-table-view-cell mui-media" v-for="item in news">
				<a  v-bind="{href:'#/news/showdetial/'+item.id}">
					<img class="mui-media-object mui-pull-left" :src="item.img_url">
					<div class="mui-media-body">
						{{item.title}}
						<p class='mui-ellipsis'>
							发表时间：{{item.add_time | dateFmt('YYYY-MM-DD	')}}
						
							<span>点击：{{item.click}}</span>
						</p>
					</div>
				</a>
			</li>
		</ul>
    </div>
</template>

<script>
import common from 'kits/common.js'
//import moment from '../../../statics/js/moment.js'

    export default{
		data(){
			return {
				news:[]
			}
		},
		created(){
			this.$http.get(common.dataApiDomain+'/api/getnewslist')
			.then((res)=>{
				this.news = res.body.message;
			});
		},
		filters:{
//			dateFmt:function(value, formatString){
//				formatString = formatString || 'YYYY-MM-DD HH:mm:ss';
//				return moment(value).format(formatString); 
//			}
		}
    }
</script>
<style scoped>
/*注意：scoped 对于通过@import 导入的css 没有用*/
  /*@import '../../../statics/css/muihead.css';*/
  
 .mui-table-view-cell > a:not(.mui-btn){
  white-space:inherit;
  }
  .mui-table-view .mui-media, .mui-table-view .mui-media-body{
  	font-size:14px;
  	color: #777777;
  }
  .mui-ellipsis{
  	color:rgba(0,148,255,0.4);
  	
  }
.mui-ellipsis > span{
	position: absolute;
	right:5px;
}
.mui-table-view{
	margin-bottom: 50px;
}
   
</style>