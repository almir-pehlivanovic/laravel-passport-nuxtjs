<template>
    <div>
        <form @submit.prevent="loginPassport">
            <label for="username">username</label>
            <input v-model="form.username" type="email" id="username">
            <br>

            <label for="password">Password</label>
            <input v-model="form.password" type="password" id="password">
            <br>

            <button>Submit</button>
        </form>
    </div>
</template>

<script>
export default {
    data(){
        return{
            form: {
                username: 'admin@admin.com',
                password: 'password',
            }
        }
    },
    methods:{
        async loginPassport(){
            await this.$auth.loginWith('laravelPassport', {data: this.form})
            .then(() =>{
                console.log("Something");
            })
            .catch((e) => {
                console.log(e);
            })
        }
    }
}
</script>