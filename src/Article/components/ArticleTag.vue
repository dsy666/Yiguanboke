<template>
	<div class="part2-2-2">
        <div id="hot-tag-box">
            <div id="hot-tag" >
              <p style="margin:0;margin-bottom:0px;">热门标签</p><br>
                <a v-for="index in tags" :key="index" href="#" :style="{fontSize:index.font_size,paddingBottom:'10px',paddingRight:'2px'}">{{ index.text }}</a>
            </div>
        </div>
        <div id="hot-artical-box">
            <div id="hot-artical" >
              <p style="margin:0;margin-bottom:0;padding:0;">热门文章</p><br>
                <li v-for="index in articals_tag.slice(0,5)" :key="index" ><a href="#" >{{ index.text }}</a></li>
            </div>
        </div>
    </div>
</template>
<script>
	export default{
		name:'ArticleTag',
		data () {
		    return {
		      msg: 'Welcome to Your Vue.js App',
		      art_page : [1,2,3,4],
		      tags:[
		      {
			      "text": "互联网金融",
			      "font_size": "16px",
			      "id": 1,
			      "url": ""
		    	},
		    {
		      "text": "APP运营",
		      "font_size": "16px",
		      "id": 2,
		      "url": ""
		    },
		    {
		      "text": "精准营销",
		      "font_size": "22px",
		      "id": 3,
		      "url": ""
		    },
		    {
		      "text": "用户体验",
		      "font_size": "12px",
		      "id": 4,
		      "url": ""
		    },
		    {
		      "text": "大数据",
		      "font_size": "28px",
		      "id": 5,
		      "url": ""
		    },
		    {
		      "text": "产品运营",
		      "font_size": "22px",
		      "id": 6,
		      "url": ""
		    },
		    {
		      "text": "Argo",
		      "font_size": "22px",
		      "id": 7,
		      "url": ""
		    },
		    {
		      "text": "广告跟踪",
		      "font_size": "12px",
		      "id": 8,
		      "url": ""
		    },
		    {
		      "text": "转化漏斗",
		      "font_size": "22px",
		      "id": 9,
		      "url": ""
		    },
		    {
		      "text": "电商",
		      "font_size": "16px",
		      "id": 10,
		      "url": ""
		    },
		    {
		      "text": "精细化运营",
		      "font_size": "28px",
		      "id": 11,
		      "url": ""
		    },
		    {
		      "text": "用户增长",
		      "font_size": "16px",
		      "id": 12,
		      "url": ""
		    },
		    {
		      "text": "数据分析",
		      "font_size": "28px",
		      "id": 13,
		      "url": ""
		    },
		    {
		      "text": "产品经理",
		      "font_size": "16px",
		      "id": 14,
		      "url": ""
		    },
		    {
		      "text": "数据驱动",
		      "font_size": "16px",
		      "id": 15,
		      "url": ""
		    },
		    {
		      "text": "用户运营",
		      "font_size": "28px",
		      "id": 16,
		      "url": ""
		    },
		    {
		      "text": "用户召回营",
		      "font_size": "16px",
		      "id": 17,
		      "url": ""
		    },
		    {
		      "text": "易观方舟",
		      "font_size": "28px",
		      "id": 18,
		      "url": ""
		    },
		    {
		      "text": "用户画像",
		      "font_size": "28px",
		      "id": 19,
		      "url": ""
		    },
		    {
		      "text": "易观开发者沙龙",
		      "font_size": "16px",
		      "id": 20,
		      "url": ""
		    }
		      ]
		      ,
		      articals_tag:[
		        {
		      "text": "电商用户生命周期价值及运营策略",
		      "url": "",
		      "id": 1,
		      "zhaiyao": "为什么要了解用户生命周期价值？这要从推广渠道价值说起，前面我们提到过易观方舟可以通过广告来源跟踪，以及判断不同流量渠道的转化率等等等",
		      "author": "赵岩",
		      "time": "2019-05-17 18:06",
		      "tag": [
		        "生命周期",
		        "电商"
		      ]
		    },
		    {
		      "text": "探寻证券数字发展，易观“证券行业数字发展”论坛圆满举办ooooo",
		      "url": "",
		      "id": 2
		    },
		    {
		      "text": "易观荣获“中国数据智能创新企业50强”",
		      "url": "",
		      "id": 3
		    },
		    {
		      "text": "数据分析里的细分维度",
		      "url": "",
		      "id": 4
		    },
		    {
		      "text": "银行产品运营如何同时分析网站和APP",
		      "url": "",
		      "id": 5
		    }
		      ]
		    }
		  }
	}
</script>
<style scoped>
.part2-2-2{
	position: absolute;
	top: 100px;
	left:65%;
  	width: 25%;
}
#secondline{
  display: none;
  float: left;
}
.artical{
    box-sizing:border-box;
    padding:20px;
    margin-top:10px;
    border-bottom:1px solid #efefef;
}
.art-right{
    float: left;
    box-sizing: border-box;
    width: calc(100% - 210px);
    padding: 10px 0 10px 20px;
}
.art-main{
    font-size: 14px;
    margin: 10px 0 5px 0;
    height: 45px;
    overflow: hidden;
    text-overflow: ellipsis;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
}
.art-main p{
  line-height: 21px;
}
.hd{
    margin: 0;
    font-size: 18px;
    display: block;
    font-weight: bold;
    cursor: pointer;
    height: 28px;
    text-align: left;
    width: 100%;
    overflow: hidden;
    white-space: nowrap;
    text-overflow: ellipsis;
    color:#333;
    line-height: 1.1;
}
.art-msg{
  height:20px;
}
.art-msg span{
  float:left;
  font-size:12px;
  line-height:18px;
  color:#999
}
.art-tag{
  max-width:194px;
  white-space:nowrap;
  text-overflow:ellipsis;
  height:20px;
  margin-top:0px;
  box-sizing:border-box;
  float:right;
  margin-left:5px;
  color: #999;
}
.art-tag a{
  line-height:20px;
  font-size:12px;
  color:#bcbcbc
}
.art-img{
  float:left;
  margin:0;
}
.pages{
  overflow: hidden;
  box-sizing: border-box;
  padding: 0 15px;
}
#page{
  float:right;
  margin: 20px 0;
}
#page a{
    position: relative;
    float: left;
    padding: 6px 12px;
    margin-left: -1px;
    line-height: 1.42857143;
    color: #337ab7;
    text-decoration: none;
    background-color: #fff;
    border: 1px solid #ddd;
    box-sizing: border-box;
    padding: 6px 12px;
    font-size: 12px;
    font-weight:500;
}
#page a:hover{
  color: #23527c;
    background-color: #eee;
    border-color: #ddd;
}
#artical-box{
  margin: 0;
  padding: 0 15px;
  box-sizing: border-box;
  //background-color: #feb167;
  float: left;
}
.artical{
  height:167px;
  //background-color: #bbb;
}
#main{
  position: relative;
}
#hot-tag-box,#hot-artical-box{
    margin: 0;
    padding: 0;
    float: left;
    display: block;
    box-sizing: border-box;
    padding:24px 24px 0 24px;
    background-color: #f9f9f9;
}
#hot-tag,#hot-artical{
    position: relative;
    text-align: left;
}
#hot-artical-box{
    margin: 20px 0 30px 0;
    width: 100%;
}
#hot-tag a{
      text-decoration: underline;
    color: #0073aa;
    flex-direction: row;
}
#hot-tag a:hover{
      color: #0097e0;
}

#hot-artical li:not(:last-of-type){
      border-bottom: 1px solid #E8E8E8;
      font-size: 13px;
      color: #000;
      cursor: pointer;
      box-sizing: border-box;
      display: block;
}
#hot-artical li{
  width: 100%;
  padding: 0;
}
#hot-artical a{
    font-size: 14px;
    height: 54px;
    line-height: 54px;
    display: block;
    text-overflow: ellipsis;
    white-space: nowrap;
    overflow: hidden;
    word-break: break-all;
    text-align: left;
}
#hot-artical a:hover{
  color: #23527c;
}
.menu-container li{
  line-height: 55px;
  color:#666;
  font-size: 14px;
  margin-right: 12px;
  box-sizing: border-box;
  padding: 0 7px;
}
#tab{
  box-sizing: border-box;
  padding:0 30px;
  border-bottom: 1px solid #d6d6d6;
  height: 56px;
  display: block;
}

.menu-container{
  overflow: hidden;
}

h1{
  margin: 0;
  padding: 0;
  font-weight: 500;
  font-size: 36px;
  padding-bottom: 40px;
  line-height: 1.1;
}

#top{
    height:80px;
    top:0;
    width: 100%;
    background-image: linear-gradient(to right,#34b4f6,#6f5af8);
    color: #fff;
    position: fixed;
    z-index: 1;
}

#header{
  width: 1920px;
  height:260px;
  position: relative;
  margin-top:80px;
  padding-top:70px;
    background-image: linear-gradient(to right,#34b4f6,#6f5af8);
    color: #fff;
    box-sizing: border-box;
}

.container{
    padding-right: 15px;
    padding-left: 15px;
    margin-right: auto;
    margin-left: auto;
}

ul{
  margin: 0;
  overflow: hidden;
}
li{
    display: inline-block;
    list-style: none;
    line-height: 80px;
    padding: 0 10px;
    float: left;
}

a{
    color: inherit;
    text-decoration: none;
    text-align: center;
    display: inline-block;
}
p{
  margin:0;
  padding:0;
}
.logo{
  float:left;
  width:132px;
  height:80px;
  margin: auto 0;
  display: table-cell;
  text-align: center;
  vertical-align: middle;
}

img{
  align-items: center;
  position: relative;
  margin-top: 10%;
}

.demo{
  float: right;
  height: 80px;
  padding-top: 20px;
}

.did{
  margin:0 auto;
  border-radius: 100px;
  font-size: 16px;
  padding: 8px 18px;
  background-image: linear-gradient(90deg,#feb167,#ff8f5f);
}
@media (min-width: 768px){
  .container{
    width:750px;
  }
  .max-760{
      width:100%;
      float: left;
    }
    .part2-2-2{
      width:100%;
      float:left;
      padding:0 15px;
      margin:0;
    }
}
@media (min-width: 992px){
    .max-760{
      width:100%;
      float: left;
    }
    .part2-2-2{
      width:100%;
      float:left;
      padding:0 15px;
      margin:0;
    }
    .container{
      width:970px;
    }
}
@media (min-width: 1200px){
  .part2-2-2{
    width:33.33333333%;
    float:left;
    padding: 0 15px 0 60px;
  }
  .max-760{
    width:66.66666666%;
    float:left;
  }
  .container{
    width:1170px;
  }
}
@media (max-width: 720px){
  .art-img{
    display: none;
  }
  .art-right{
    width:100%;
    padding:0;
  }
  .artical{
    padding:0;
  }
  .max-760{
    width:100%;
    overflow: hidden;
  }
  #inline{
    display: none;
  }
  #secondline{
      display: block;
  }
}
</style>