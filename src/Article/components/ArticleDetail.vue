<template>
	<div class="view">
		<div class="place">当前位置：<span>易观方舟></span><span>知识库></span><span>{{article.title}}</span></div>
		<h3>{{article.title}}</h3>
		<i class="iconfont icon-yonghu"></i>
		<span class="issueTime">易观 {{article.issueTime}}</span>
		<span v-for="item in article.tagList" class="tagList">{{item.tagName}}</span>
		<i class="iconfont icon-biaoqian1"></i>
		<div class="articleDetail" v-html="article.content"></div>
		<span class="previous" v-if="preshow"><a>上一篇：{{previous.title}}</a></span>
		<span v-else>已经是最新文章了</span>
		<span class="next" v-if="nextshow"><a>下一篇：{{next.title}}</a></span>
		<span class="next" v-else>已经是最后一篇文章了</span>
	</div>
</template>
<script>
import VueEvent from '@/module/VueEvent.js'
import axios from 'axios'
export default{
	name:"Articalhome",
	data(){
		return {
			//数据存储尽量用对象
			// articleId:1,
			// title:"网站运营需要关注哪些数据?",
			// author:"赵岩",
			// date:"2019-04-22 10:08",
			// tab1:"网站运营",
			// tab2:"数据指标",
			// tab3:"获客",
			// artical:{},
			// prev:" 电商用户生命周期价值及运营策略",
			// next:"易观荣获“中国数据智能创新企业50强”",
			// articlePojoList:[],
			// num:1,
			// url:''
			preshow:true,
			nextshow:true,
			article:{},
			previous:{},
			next:{},
			inputArticleId: ''

		}
	},
	props:['articleId'],
	created(){
		// const self=this
		// VueEvent.$on('Val',(val)=>{
		// 	if(val==1){
		// 		self.loc='/static/mock/index.json'
		// 	}else{
		// 		self.loc='/static/mock/main.json'
		// 	}
		// })

		this.getArticle(17)
	},
	methods:{
		getArticle(articleId){
			let params = new URLSearchParams();
			params.append("articleId", articleId)
			// axios封装
	  		axios({
	  			url:'http://106.13.226.142:8093/api/blog/getArticle',
	  			method:'post',
	  			// headers:{
      //   			'Content-type': 'application/x-www-form-urlencoded'
    		// 	},
	  			data: params
	  			// transformRequest: [function (data) {
			   //     let ret = ''
			   //     for (let it in data) {
			   //     ret += encodeURIComponent(it) + '=' + encodeURIComponent(data[it]) + '&'
			   //   }
			   //    return ret
			   //  }]
	  		})
	  		  .then(this.handleArticleInfoSucc)

	  		  // this.$http.post('http://10.161.56.34:8080/blog/frontAndNext', {
	  		  // 	articleId: 15
	  		  // }).then((data) => {
	  		  // 	console.log('dfssfdsdf')
	  		  // })

	  		  // let params = new URLSearchParams();
	  		  // params.append('articleId', 1)

	  		  // this.$ajax({
	  		  // 	method:'post',
	  		  // 	url:'/api/blog/getArticle',
	  		  // 	data:params
	  		  // }).then((response => {
	  		  // 	console.log(response)
	  		  // }))

	  		 //  axios({
	  		 //  	url:'http://106.13.226.142:8093/api/blog/tag/getPopularTag',
	  			// method:'post',
	  		 //  }).then(this.handleArticleInfoSucc)
  		},
  		handleArticleInfoSucc(res){
  			// res=res.data
	  		// if(res.result&&res.data){
	  		// 	console.log(res)
	  		// }
	  		this.article = res.data.data.article
        	this.previous = res.data.data.previous
        	this.next = res.data.data.next
        	if(!this.previous){
				this.preshow=false
			}
			if(!this.next){
				this.nextshow=false
			}
  		},
  		getPrevious() {
      		this.getArticle(this.previous.articleId)
    	},
    	getNext() {
      		this.getArticle(this.next.articleId)
    	},
    	search(event) {
	      console.log(this.inputArticleId)
	      this.getArticle(this.inputArticleId)
	      this.inputArticleId = ''
	    }
	}
	
}
</script>
<style scoped>
	*{
		margin:0;
		padding:0;
	}
	.view{
		width: 60%;
		margin-left: 5%;
		margin-bottom: 20px;
	}
	.place{
		font-size: 13px;
	}
	h3{
		font-weight: bold;
		margin-top: 10px;
		margin-bottom: 20px;
	}
	.issueTime{
		margin-right: 50px;
		font-size: 10px;
	}
	.tagList{
		margin-right: 5px;
		font-size: 10px;
		float: right;
	}
	.iconfont{
		font-size: 10px;
	}
	.icon-biaoqian1{
		float: right;
	}
	.articleDetail{
		margin-top: 15px;
		border-top: 1px solid #696969;
		border-bottom: 1px solid #696969;
	}
	.next{
		float: right;
	}
	a{
		text-decoration: none;
		cursor: pointer;
	}
</style>