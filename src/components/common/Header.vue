<template>
    <div class='Container'>
        <h1>나만의 쇼핑몰</h1>
        <div class='loginForm'>
            <p @click='onClickRegister'>회원가입</p>
            <p @click='onClickLogin'>로그인</p>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return {
            loginStatus: false,
            id : '',
            password: '',
        }
    },
    methods: {
        onClickRegister() {
            console.log('register');
        },
        onClickLogin() {
            console.log('login');
        }
    },
}
</script>

<style scoped>
    h1{
        text-align : center;
        font-weight: 30px;
        width: 80%
    }
    
    .loginForm {
        display: flex;
        width: 20%;
    }
    
    p {
        text-align: right;
        margin : 5px 10px 5px 10px;
        
    }
    .Container {
        width: 100%;
        display: flex;
    }
</style>

