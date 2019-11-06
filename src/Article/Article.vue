<template>
	<div>
		<article-header></article-header>
		<article-detail></article-detail>
		<article-tag></article-tag>
		<article-bottom></article-bottom>
	</div>
</template>
<script>
	import ArticleDetail from './components/ArticleDetail'
	import ArticleHeader from './components/ArticleHeader'
	import ArticleBottom from './components/ArticleBottom'
	import ArticleTag from './components/ArticleTag'
	export default{
		name:'Article',
		components:{
			ArticleDetail,
			ArticleHeader,
			ArticleBottom,
			ArticleTag
		}
}
</script>