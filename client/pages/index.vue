<template>
  <div>
    <v-sheet>
      <v-container class="py-6 pt-lg-15 text-center">
        <h1 class="text-h4 text-sm-h3 text-md-h2 text-lg-h1"><span class="primary--text">友達を見つけよう</span></h1>
        <h2 class="text-h6 text-sm-h5 mt-4 w-full w-md-8-12 w-xl-half mx-auto">一人ではなくみんなで共有して励まし合いながらダイエットを頑張りましょう</h2>
        <div class="mt-8">
          <NuxtLink to="/auth/signin">Signin</NuxtLink>
        </div>
      </v-container>
    </v-sheet>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  methods: {
    api() {
      this.$axios.get('/').then((res) => {
        console.log(res)
      })
    },
  },
}
</script>
