<template>
    <div>
        <el-form ref="form" :model="loginForm">
            <h3>欢迎登陆</h3>
            <el-form-item>
                <el-input type="text" autocomplete="false" v-model="loginForm.username" placeholder="请输入用户名"></el-input>
            </el-form-item>
            <el-form-item>
                <el-input type="password" autocomplete="false" v-model="loginForm.password"
                          placeholder="请输入密码"></el-input>
            </el-form-item>
            <el-checkbox v-model="checked">记住我</el-checkbox>
            <el-button type="primary" style="width:100%">登陆</el-button>
        </el-form>
    </div>
</template>

<script>
    export default {
        name: "Login",
        data() {
            return {
                checked: false,
                loginForm: {
                    username: "admin",
                    password: "123",
                },
            };
        },
        components: {},
    };
</script>

<style>
</style>
