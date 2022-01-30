<template>
    <form>
        <label>Email:</label>
        <input type="email" required v-model="email">
        <label>Password: </label>
        <input type="password" required v-model="password">

        <label>Role:</label>
        <select v-model="role">
            <option value="Backend Developer">Backend Developer</option>
            <option value="Frontend Developer">Frontend Developer</option>
            <option value="UI/UX Designer">UI/UX Designer</option>
        </select>
    </form>
    <p>email: {{ email }}</p>
    <p>password: {{ password }}</p>
    <p>Role: {{ role }}</p>
</template>

<script>
export default {
    data() {
        return {
            email: '',
            password: '',
            role: ''
        }
    },
    methods: {

    }
}
</script>
