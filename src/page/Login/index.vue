<template>
  <div class="login">
    <img alt="Vue logo" :src="require('assets/logo.png')">
    <LoginRe />
  </div>
</template>

<script>
import components from 'components';
const { LoginRe } = components

export default {
    name: 'Login',
    props: {
        msg: String
    },
    components: {
        LoginRe,
    }
}
</script>

<style lang="scss" scoped>
.login{
    width: 100%;
    height: 100%;
    background: salmon;
    position: relative;
    img{
        position: absolute;
        top: 4%;
        left: 6%;
        width: 80px;
        height: 80px;
    }
}
</style>