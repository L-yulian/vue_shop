<template>
    <div class="login_container">
        <div class="login_box">
            <div class="avatar_box">
                <img src="../assets/logo.png" alt="">
            </div>
            <!-- 登录区域 -->
            <el-form ref="form" :model="loginForm" :rules="loginFormRules" label-width="0px" class="login_form">
                <!-- 用户名 -->
                <el-form-item prop="username">
                  <el-input v-model="loginForm.username" prefix-icon="iconfont icon-user"></el-input>
                </el-form-item>
                <!-- 密码 -->
                <el-form-item prop="password">
                  <el-input type="password" v-model="loginForm.password" prefix-icon="iconfont icon-3702mima"></el-input>
                </el-form-item>
                <!-- 按钮 -->
                <el-form-item class="btns">
                    <el-button type="success">登录</el-button>
                    <el-button type="info">重置</el-button>
                </el-form-item>
            </el-form>
        </div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            loginForm:{
                username:'',
                password:''
            },
            // 表单验证规则
            loginFormRules:{
                // 用户验证
                username:[
                    {required:true,message:'请输入用户名',tigger:'blur'},
                    {min:3,max:5,message:'长度在 3 到 5 个字符',trigger:'blur'}
                ],
                password:[
                    {required:true,message:'请输入密码',tigger:'blur'},
                    {min:3,max:5,message:'长度在 3 到 5 个字符',trigger:'blur'}
                ]
            }
        }
    },
}
</script>

<style lang="less" scoped>
.login_container{
    width: 100%;
    height: 100%;
    background-color: #2d4d6d;
}

.login_box{
    width: 450px;
    height: 300px;
    background-color: #fff;
    position: relative;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%);
    .avatar_box{
        width: 130px;
        height: 130px;
        padding: 10px;
        border: 1px solid #eee;
        border-radius: 50%;
        box-shadow: 0 0 10px #ddd;
        background-color: #fff;
        position: absolute;
        left: 50%;
        transform: translate(-50%,-50%);
        img{
            width: 100%;
            height: 100%;
            border-radius: 50%;
            background-color: #eee;
        }
    }
}

.login_form{
    position: absolute;
    bottom: 0;
    width: 100%;
    padding: 0 20px;
    box-sizing: border-box;
}
.btns {
    display:flex;
    justify-content: flex-end;
}
</style>