<template class="allUsers">
    <div>
        <User v-for="user in userList" :key="user.id" :user="user"/>
    </div>
</template>
<script>
import User from './User.vue';

export default {
    components: {
        User
    },
    name: 'UserList',
    data() {
        return {
            userList: [
                {
                    name: 'Slava',
                    lastName: 'Dobrov',
                    email: 'dobrov1@ya.ru'
                },
                {
                    name: 'Oleg',
                    lastName: 'Dobrov',
                    email: 'dobrov2@ya.ru'
                },
                {
                    name: 'Sveta',
                    lastName: 'Dobrova',
                    email: 'dobrova@ya.ru'
                }
            ]
        }
    }
}
</script>
<style lang="scss">
.allUsers {
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 20px;
    padding-right: 200px;
    padding-left: 200px;
    border: 1px red solid;
}
</style>