<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8 card-position-center">
                <div class="card">
                    <div class="card-header">Login</div>
                    <div class="card-body">
                        <form>
                            <div class="form-group row">
                                <label for="email" class="col-md-4 col-form-label text-md-right">E-Mail Address</label>
                                <div class="col-md-6">
                                    <input id="email" type="email" class="form-control" name="email" required autocomplete="email" autofocus v-model="email">
                                </div>
                            </div>

                            <div class="form-group row">
                                <label for="password" class="col-md-4 col-form-label text-md-right">Password</label>
                                <div class="col-md-6">
                                    <input id="password" type="password" class="form-control" name="password" required autocomplete="current-password" v-model="password">
                                </div>
                            </div>

                            <div class="form-group row">
                                <div class="col-md-6 offset-md-4">
                                    <div class="form-check">
                                    <input class="form-check-input" type="checkbox" name="remember" id="remember" v-model="remember">

                                    <label class="form-check-label" for="remember">
                                        Remember Me
                                    </label>
                                    </div>
                                </div>
                            </div>

                            <div class="form-group row mb-0">
                                <div class="col-md-8 offset-md-4">
                                    <button @click="login" class="btn btn-primary">
                                    Login
                                    </button>
                                    <a class="btn btn-link" href="">
                                        Forgot Your Password?
                                    </a>
                                </div>
                            </div>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {

        data() {
            return {
            email: null,
            password: null,
            remember: null,
            loading: false
            }
        },

        methods: {
            login() {
                window.axios.post('login', {
                    email: this.email, password: this.password
                })
                    .then(response => {
                    console.log('Login fired!')
                    console.log(response.data)
                    })
                    .catch(error => {
                    console.log(error)
                    })
                },
        },
    }
</script>

