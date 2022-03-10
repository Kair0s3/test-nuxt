<template>
  <div>
    <h1> {{title}} </h1>
    <p>
      The user's address you are viewing is {{$route.params.userAddress}}
    </p>
    <p v-pre>
      Note that you can access the route params using {{$route.params.dynamicRouteName}}
    </p>
    <NuxtLink to="/">
      Back to home!
    </NuxtLink>
  </div>
</template>

<script>
export default {
  name: 'UserPage',
  data () {
    return {
      title: "Testing file name as dynamic route"
    }
  }
}
</script>
