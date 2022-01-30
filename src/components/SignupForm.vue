<template>
    <form>
        <label>Email:</label>
        <input type="email" required v-model="email">
        <label>Password: </label>
        <input type="password" required v-model="password">

        
    </form>
    <p>email: {{ email }}</p>
    <p>password: {{ password }}</p>
</template>

<script>
export default {
    data() {
        return {
            email: '',
            password: ''
        }
    },
    methods: {

    }
}
</script>
