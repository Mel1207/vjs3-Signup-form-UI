<template>
    <form @submit.prevent="handleSubmit">
        <label>Email:</label>
        <input type="email" required v-model="email">
        <label>Password: </label>
        <input type="password" required v-model="password">
        <div v-if="passwordError" class="error">
            {{ passwordError }}
        </div>

        <label>Role:</label>
        <select v-model="role">
            <option value="Backend Developer">Backend Developer</option>
            <option value="Frontend Developer">Frontend Developer</option>
            <option value="UI/UX Designer">UI/UX Designer</option>
        </select>

        <label>Skills</label>
        <input type="text" v-model="tempSkill" @keyup.alt="addSkill">
        <div v-for="skill in skills" :key="skill" class="pill">
            <span @click="deleteSkill(skill)">{{ skill }}</span>
        </div>

        <div class="terms">
            <input type="checkbox" required v-model="terms">
            <label>Accept Terms and conditions</label>
        </div>

        <div class="submit">
            <button>Create an Account </button>
        </div>
    </form>
   
    <p>email: {{ email }}</p>
    <p>password: {{ password }}</p>
    <p>Role: {{ role }}</p>
    <p>Terms accepted: {{ terms }}</p>
</template>

<script>
export default {
    data() {
        return {
            email: '',
            password: '',
            role: '',
            terms: false,
            tempSkill: '',
            skills: [],
            passwordError: ''
        }
    },
    methods: {
        addSkill(e) {
            if(e.key === ',' && this.tempSkill) {
                if(!this.skills.includes(this.tempSkill)) {
                    this.skills.push(this.tempSkill)
                }
                this.tempSkill = ''
            }
        },
        deleteSkill(skill) {
            this.skills = this.skills.filter((item) => {
                return skill !== item
            })
        },
        handleSubmit() {
            // console.log('form submitted')
            this.passwordError = this.password.length > 5 ? '' : 'Password must be at least 6 characters long'


            if (!this.passwordError) {
                console.log('email: ', this.email)
                console.log('password: ', this.password)
                console.log('role: ', this.role)
                console.log('skills: ', this.skills)
                console.log('terms: ', this.terms)
            }
        }
    }
}
</script>
