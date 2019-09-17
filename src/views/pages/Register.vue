<!-- =========================================================================================
    File Name: Register.vue
    Description: Register Page
    ----------------------------------------------------------------------------------------
    Item Name: Vuesax Admin - VueJS Dashboard Admin Template
      Author: Pixinvent
    Author URL: http://www.themeforest.net/user/pixinvent
========================================================================================== -->


<template>
    <div class="h-screen flex w-full bg-img vx-row no-gutter items-center justify-center">
        <div class="vx-col sm:w-1/2 md:w-1/2 lg:w-3/4 xl:w-3/5 sm:m-0 m-4">
            <vx-card>
                <div slot="no-body" class="full-page-bg-color">
                    <div class="vx-row no-gutter">
                        <div class="vx-col hidden sm:hidden md:hidden lg:block lg:w-1/2 mx-auto self-center">
                            <img src="@/assets/images/pages/register.jpg" alt="register" class="mx-auto">
                        </div>
                        <div class="vx-col sm:w-full md:w-full lg:w-1/2 mx-auto self-center  d-theme-dark-bg">
                            <div class="p-8">
                                <div class="vx-card__title">
                                    <h4 class="mb-4">Inscribete y comienza a explorar.</h4>
                                    <p>Llene todos los campos para crear una nueva cuenta.</p>
                                </div>
                                <div class="clearfix">
                                    <vs-input
                                        v-validate="'required|min:4'"
                                        data-vv-validate-on="blur"
                                        label-placeholder="nombre"
                                        name="nombre"
                                        placeholder="Nombre(s)"
                                        v-model="nombre"
                                        class="w-full" />
                                    <span class="text-danger text-sm">{{ errors.first('nombre') }}</span>

                                    <vs-input
                                        v-validate="'required|min:4'"
                                        data-vv-validate-on="blur"
                                        label-placeholder="apellido"
                                        name="apellido"
                                        placeholder="Apellidos"
                                        v-model="apellido"
                                        class="w-full" />
                                    <span class="text-danger text-sm">{{ errors.first('apellido') }}</span>

                                    <vs-input
                                        v-validate="'required|alpha_dash|min:3'"
                                        data-vv-validate-on="blur"
                                        label-placeholder="Username"
                                        name="username"
                                        placeholder="Usuario"
                                        v-model="username"
                                        class="w-full" />
                                    <span class="text-danger text-sm">{{ errors.first('username') }}</span>

                                    <vs-input
                                        v-validate="'required|email'"
                                        data-vv-validate-on="blur"
                                        name="email"
                                        type="email"
                                        label-placeholder="Email"
                                        placeholder="Correo electronico"
                                        v-model="email"
                                        class="w-full mt-6" />
                                    <span class="text-danger text-sm">{{ errors.first('email') }}</span>

                                    <vs-input
                                        ref="password"
                                        type="password"
                                        data-vv-validate-on="blur"
                                        v-validate="'required|min:6|max:10'"
                                        name="password"
                                        label-placeholder="Password"
                                        placeholder="Contraseña"
                                        v-model="password"
                                        class="w-full mt-6" />
                                    <span class="text-danger text-sm">{{ errors.first('password') }}</span>

                                    <vs-input
                                        type="password"
                                        v-validate="'min:6|max:10|confirmed:password'"
                                        data-vv-validate-on="blur"
                                        data-vv-as="password"
                                        name="confirm_password"
                                        label-placeholder="Confirm Password"
                                        placeholder="Confirmar Contraseña"
                                        v-model="confirm_password"
                                        class="w-full mt-6" />
                                    <span class="text-danger text-sm">{{ errors.first('confirm_password') }}</span>

                                    <vs-checkbox v-model="isTermsConditionAccepted" class="mt-6">Acepto los terminos y condiciones</vs-checkbox>
                                    <vs-button  type="border" to="/pages/login" class="mt-6">Iniciar Sesion</vs-button>
                                    <vs-button class="float-right mt-6" @click="registerUser" :disabled="!validateForm">Registrar</vs-button>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </vx-card>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            nombre: '',
            apellido: '',
            username: '',
            email: '',
            password: '',
            confirm_password: '',
            isTermsConditionAccepted: true
        }
    },
    computed: {
        validateForm() {
            return !this.errors.any() && this.nombre != '' && this.apellido != '' && this.username != '' && this.email != '' && this.password != '' && this.confirm_password != '' && this.isTermsConditionAccepted === true;
        }
    },
    methods: {
        registerUser() {
            if (!this.validateForm) return false
            if(this.$store.state.auth.isUserLoggedIn()) {
              this.notifyAlreadyLogedIn();
              return
            }
            const payload = {
              userDetails: {
                nombre: this.nombre,
                apellido: this.apellido,
                email: this.email,
                password: this.password,
                username: this.username
              },
              notify: this.$vs.notify
            }
            this.$store.dispatch('auth/registerUser', payload)
        },
        notifyAlreadyLogedIn() {
            this.$vs.notify({
                title: 'Login Attempt',
                text: 'You are already logged in!',
                iconPack: 'feather',
                icon: 'icon-alert-circle',
                color: 'warning'
            });
        },
    }
}
</script>
