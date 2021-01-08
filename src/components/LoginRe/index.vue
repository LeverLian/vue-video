<template>
    <div class="loginRe">
        <div class="login-header">
            <span v-on:click="change(true)" :class="{selected: select}">账号注册</span>
            <span v-on:click="change(false)" :class="{selected: !select}" >密码登录</span>
        </div>
        <div class="login-body" v-if="!select">
            <Input
                placeholder="请输入账号"
                v-model="loginId"
                clearable
                class="login-input"
            />
            <Input
                placeholder="请输入密码"
                v-model="password"
                clearable
                class="login-input"
                show-password
            />
            <Button class="login-button">登录</Button>
        </div>
        <div class="login-body" v-if="select">
            <Input
                placeholder="请输入账号"
                v-model="loginId"
                clearable
                class="login-input"
            />
            <Input
                placeholder="请输入密码"
                v-model="password"
                clearable
                class="login-input"
                show-password
            />
            <Input
                placeholder="请再次输入密码"
                v-model="passwordT"
                clearable
                class="login-input"
                show-password
            />
            <Button class="login-button">注册</Button>
        </div>
    </div>
</template>

<script>
import {Input, Button} from 'element-ui'

export default {
    components:{
        Input,
        Button
    },
    data(){  //为了保证每个组件的实例数据是独立的
        return {
            select: false, //选择的内容
            loginId: "", //账号
            password: "", //密码
            passwordT: "", //重复密码
        }
    },
    methods:{
        change: function (params) {
            this.select = params
        },
    }
}
</script>

<style lang="scss" scoped>
.loginRe{
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-90%);
    width: 340px;
    background: #fff;
    border-radius: 12px;
    .login-header{
        padding: 20px 20px 10px 20px;
        display: flex;
        justify-content: center;
        font-size: 14px;
        font-weight: 600;
        color: #666;
        span{
            padding: 10px 20px;
            margin: 0 20px;
            text-align: center;
            cursor: pointer;
            }
        .selected{
            border-bottom: 2px solid coral;
            color: coral;
        }
    }
    .login-body{
        margin: 0 0 10px 0;
        .login-input{
            width: 80%;
            height: 30px;
            margin: 12px 0
        }
        .login-button{
            background: coral;
            color: #fff;
            width: 80%;
            height: 40px;
            margin: 20px 0;
            font-weight: 600;
        }
    }
}
</style>