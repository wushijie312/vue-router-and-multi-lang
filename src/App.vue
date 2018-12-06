<template>
  <div id="app">
    <head-top @changeAppLocale="changeAppLocale" v-bind:lang="lang">HeadTop </head-top>
    <div class="main">
      <router-view v-bind:lang="lang"></router-view>
    </div>
    <footer-bottom></footer-bottom>
    </div>
</template>

<script type="es6">
import HeadTop from "./components/Header"
import FooterBottom from "./components/Footer"

export default {
  name: 'app',
  data(){
    return{
      lang: ''
    }
  },
  components:{
    HeadTop,
    FooterBottom,
	},
  methods:{
    changeLanguage(lang){
      this.$i18n.locale=lang;
      this.lang=lang;
    },
		changeAppLocale(locale){
      this.changeLanguage(locale);
      this.$router.push({name: this.$route.name, params: {lang: this.lang}})
		}
	},
	mounted(){
    this.changeLanguage(this.$route.params.lang);
	}
}
</script>

<style scoped>
  @import './style/common.css';
  
</style>
