<template>
    <div class="form" v-if="!isAuth">
        <div class="form__box">
            <h3 class="form__text">Введите имя пользователя:</h3>
            <input type="text" class="form__input" v-model="userName">
        </div>
        <div class="form__box">
            <h3 class="form__text">Введите пароль:</h3>
            <input type="password" class="form__input" v-model="userPassword">
        </div>
        <button class="form__confirm" @click="confirm">Пройти аутентификацию</button>
    </div>
    <div class="form__success" v-else>
        <h2 class="form__text_big">Аутентификация прошла успешно!</h2>
    </div>
    <h2 class="form__error" v-if="isError">Неправильное имя пользователя или пароль!</h2>
</template>
<script>
export default {
    name: 'autentification',
    props: {
        isAuth: Boolean
    },
    data() {
        return {
            name: 'Slava',
            password: '12345',
            userName: '',
            userPassword: '',
            isError: false
        }
    },
    // methods: {
    //     confirm() {
    //         if(this.name === this.userName && this.password === this.userPassword) {
    //             this.isAuthenticated = true;
    //             this.isError = false;
    //         } else {
    //             this.isAuthenticated = false;
    //             this.isError = true;
    //         }
    //     },
    // }
}
</script>
<style lang="scss">
    
</style>