<template>
    <div class="card">
        <h2 class="card__name"> Name: {{ user.name }}</h2>
        <h2 class="card__surname">Surname: {{ user.lastName }}</h2>
        <h2 class="card__email">Email: {{ user.email }}</h2>
    </div>
</template>
<script>
export default {
    name: 'User',
    props : {
        user: Object
    }
}
</script>
<style lang="scss">
.card {
    display: flex;
    flex-direction: row;
    justify-content: center;
    gap: 20px;
    align-content: center;
    border: 1px green solid;
}
</style>