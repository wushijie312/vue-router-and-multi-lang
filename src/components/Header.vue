<template >
		<div class="header-language" v-bind:class="lang">
			<span> 点击选择语言：</span>
			<span class="en" @click="changeLocale('en')"> English</span>
			<span class="zhCHS" @click="changeLocale('zhCHS')"> 简体中文</span>
			<span class="zhCHT" @click="changeLocale('zhCHT')"> 繁體中文</span>
			<p> current language: {{lang}}</p>
			<p class="tip" 蓝框中为多语言区域</p>
	</div>
</template>

<script type="es6">
export default {
	props:['lang'],
  methods:{
		changeLocale(locale){
			this.$emit('changeAppLocale',locale);
		}
  }
}
</script>

<style scoped>
.header-language{
		color: red;
		}
	*{
		margin: 0 5px;
	}
	.tip{
		color: grey;
		font-size: 12px;
		margin-top: .5em;
		}
</style>
