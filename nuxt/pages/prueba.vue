<template>
    <div>
        <h1>
            aca van las pruebas
            <b-badge href="#" variant="success">Sucddccess</b-badge>
        </h1>

        <!--<div v-for="user in users" :key="user.id">-->
            <!--<span v-text="user.name"></span>-->
        <!--</div>-->

        <div class="text-center">
            <b-button variant="primary">
                Notifications <b-badge variant="light">4</b-badge>
            </b-button>
        </div>
    </div>
</template>

<script>
    export default {
        name: "prueba",
        auth: false,
        // data(){
        //     return {
        //         users: []
        //     }
        // },
        // created(){
        //     this.getUsers
        // },
        // methods: {
        //     async getUsers() {
        //         try {
        //           await this.$axios.$get('/users')
        //               .then(res =>{
        //                   console.log(res)
        //                   return {
        //                       users:res.data
        //                   }
        //               })
        //         }catch (e) {
        //             return;
        //         }
        //
        //     },
        //
        // }
    }
</script>