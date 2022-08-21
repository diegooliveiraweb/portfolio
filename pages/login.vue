<template>
  <section class="section">
    <div class="container">
      <div class="columns is-centered">
        <div class="column is-one-third">
          <h2 class="title has-text-centered">Login</h2>

          <form method="post" @submit.prevent="login">
            <div label="Email">
              <input
                type="email"
                v-model="email"
                required
              >
            </div>

            <div label="Password">
              <input
                type="password"
                v-model="password"
                required>
            </div>

            <button type="submit">
              Login
            </button>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  data() {
    return {
      email: '',
      password: '',
    }
  },
  methods: {
    async login() {
      await this.$auth.loginWith('laravelSanctum', {
        data: {
          email: this.email,
          password: this.password,
        },
      })
        console.log(this.$auth.user.data);
     this.$router.push('/')
    },
  },
}
</script>