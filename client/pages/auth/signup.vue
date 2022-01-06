<template>
  <row>
    <v-col cols="12">
      <v-card class="text-center pa-1">
        <v-card-title class="justify-center display-1 mb-2"
          >Welcome</v-card-title
        >
        <v-card-subtitle>Signup to your account</v-card-subtitle>
        <v-card-text>
          <v-form ref="form" v-model="isFormValid" lazy-validation>
            <v-text-field
              v-model="name"
              :rules="[rules.required]"
              :validate-on-blur="false"
              :error="error"
              label="Name"
              name="name"
              outlined
              @keyup.enter="submit"
              @change="resetErrors"
            ></v-text-field>

            <v-text-field
              v-model="password"
              :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
              :rules="[rules.required]"
              :type="showPassword ? 'text' : 'password'"
              :error="error"
              :error-messages="errorMessages"
              label="Password"
              name="password"
              outlined
              @change="resetErrors"
              @keyup.enter="submit"
              @click:append="showPassword = !showPassword"
            ></v-text-field>

            <v-btn
              :loading="isLoading"
              :disabled="isSignUpDisabled"
              block
              x-large
              color="primary"
              @click="submit"
              >SignUp</v-btn
            >

            <div v-if="errorProvider" class="error--text">
              {{ errorProviderMessages }}
            </div>
          </v-form>
        </v-card-text>
      </v-card>
    </v-col>

    <div class="text-center mt-6">
      <router-link to="/auth/signin" class="font-weight-bold">
        Login Account
      </router-link>
    </div>
  </row>
</template>

<script>
export default {
  data() {
    return {
      // sign in buttons
      isLoading: false,
      isSignUpDisabled: false,

      // form
      isFormValid: true,
      name: '',
      password: '',

      // form error
      error: false,
      errorMessages: '',

      errorProvider: false,
      errorProviderMessages: '',

      // show password field
      showPassword: false,

      providers: [
        {
          id: 'google',
          label: 'Google',
          isLoading: false,
        },
        {
          id: 'facebook',
          label: 'Facebook',
          isLoading: false,
        },
      ],

      // input rules
      rules: {
        required: (value) => (value && Boolean(value)) || 'Required',
      },
    }
  },
  methods: {
    submit() {
      if (this.$refs.form.validate()) {
        this.isLoading = true
        this.isSignUpDisabled = true
        this.signUp(this.email, this.password)
      }
    },
    signUp(email, password) {
      this.$router.push('/')
    },
    signUpProvider(provider) {},
    resetErrors() {
      this.error = false
      this.errorMessages = ''

      this.errorProvider = false
      this.errorProviderMessages = ''
    },
  },
}
</script>
