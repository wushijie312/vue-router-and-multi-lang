<template>
  <div class="about" >
    <h3 class="content"> {{ $t("message.about") }}</h3>
    <router-link :to="{name:'home',params: {lang: this.lang}}"> link to Home</router-link>
    
    </div>
</template>

<script type="es6">
  export default {
    name:'about',
    props: ['lang']
  }
</script>


