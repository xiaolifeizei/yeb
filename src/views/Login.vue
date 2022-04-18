<template>
    <div>
        <el-form ref="loginForm" :rules="rules" :model="loginForm" class="loginContenner">
            <h3 class="loginTitle">欢迎登陆</h3>
            <el-form-item prop="username">
                <el-input type="text" autocomplete="false" v-model="loginForm.username" placeholder="请输入用户名"></el-input>
            </el-form-item>
            <el-form-item prop="password">
                <el-input type="password" autocomplete="false" v-model="loginForm.password"
                          placeholder="请输入密码"></el-input>
            </el-form-item>
            <el-checkbox v-model="checked" style="margin: 0 0 10px 0">记住我</el-checkbox>
            <el-button type="primary" style="width:100%" @click="doLogin">登陆</el-button>
        </el-form>
    </div>
</template>

<script>
    export default {
        name: "Login",
        data() {
            return {
                checked: true,
                loginForm: {
                    username: "admin",
                    password: "123",
                },
                rules:{
                    username: [{required: true,message:'请输入用户名',trigger:'blur'}],
                    password: [{required:true,message:'请输入密码',trigger:'blur'}]
                }
            };
        },
        methods: {
            doLogin() {
                this.$refs.loginForm.validate((valid)=>{
                    if (valid) {
                        alert(1111)
                    } else {
                        this.$message({type: 'error', message: `请输入用户名或密码`});
                    }
                });
            }
        },
        components: {},
    };
</script>

<style>
    .loginContenner {
        border-radius: 15px;
        background-clip: padding-box;
        margin: 188px auto;
        width: 350px;
        padding: 15px 35px 15px 35px;
        background: #fff;
        border: 1px solid #eaeaea;
        box-shadow: 0 0 25px #cac6c6;
    }
    .loginTitle{
        margin: 0 auto 40px auto;
        text-align: center;

    }
</style>
