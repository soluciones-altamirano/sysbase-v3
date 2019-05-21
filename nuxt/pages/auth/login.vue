<template>
  <div class="app flex-row align-items-center">
    <div class="container">
      <b-row class="justify-content-center">
        <b-col md="8">
          <b-card-group>
            <b-card no-body class="p-4">
              <b-card-body>
                <h1>Login</h1>
                <p class="text-muted">Sign In to your account</p>

                <form @submit.prevent="login">
                <b-input-group class="mb-3">

                  <b-input-group-prepend><b-input-group-text>@</b-input-group-text></b-input-group-prepend>
                  <input type="email" class="form-control" v-model="form.email" :class="{ 'is-invalid': errors.email }" placeholder="Email">
                  <div class="invalid-feedback" v-if="errors.email">
                    {{errors.email[0]}}
                  </div>
                </b-input-group>
                <b-input-group class="mb-4">
                  <b-input-group-prepend><b-input-group-text><i class="icon-lock"></i></b-input-group-text></b-input-group-prepend>
                  <input type="password" class="form-control" v-model="form.password" :class="{ 'is-invalid': errors.password }" placeholder="Password">
                  <div class="invalid-feedback" v-if="errors.password">
                    {{errors.password[0]}}
                  </div>
                </b-input-group>
                <b-row>
                  <!--<b-col cols="6">-->
                    <input type="submit" class="btn btn-primary px-4 col-6" value="Login">
                    <!--<b-button variant="primary" class="px-4">Login</b-button>-->
                  <!--</b-col>-->


                  <b-col cols="6" class="text-right">
                    <b-button variant="link" class="px-0">Forgot password?</b-button>
                  </b-col>
                </b-row>

                </form>
              </b-card-body>
            </b-card>
            <b-card no-body class="text-white bg-primary py-5 d-md-down-none" style="width:44%">
              <b-card-body class="text-center">
                <div>
                  <h2>Sign up</h2>
                  <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
                  <NuxtLink to="/auth/register">
                    <b-button variant="primary" class="active mt-3">Register Now!</b-button>
                  </NuxtLink>
                </div>
              </b-card-body>
            </b-card>
          </b-card-group>
        </b-col>
      </b-row>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Login',
  layout: 'clean',
    data(){
        return {
            form: {
                email:'',
                password:'',
            }
        }
    },
    methods: {
        async login(){

            try {
                await this.$auth.login({data: this.form});
            } catch(e) {
                return;
            }

            this.$router.push({ name: 'index' });

        }
    }
}
</script>
