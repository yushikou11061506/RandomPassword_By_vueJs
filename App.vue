<template>
    <div>
        <h1>Generate Password</h1>
        <input type="number" v-model.number="length" min="4" />
        <button @click="generatePassword">Generate Password</button>
        <p>{{ password }}</p>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                length: 8,
                password: ''  // セミコロンではなくカンマを使用
            };
        },
        methods: {
            generatePassword() {
                let str = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789";
                let newPassword = "";
                for (let i = 0; i < this.length; i++) {
                    newPassword += str.charAt(Math.floor(Math.random() * str.length));
                }
                this.password = newPassword;
            }
        }
    };
</script>

<style scoped>

    h1{
        text-align:center;
        color:blue;
    }

    input{
        text-align:end;
    }



</style>
