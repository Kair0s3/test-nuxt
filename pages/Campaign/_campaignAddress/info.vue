<template>
  <div>
    <h1> {{ title }} </h1>
    <p>
      The campaign address you are viewing is {{$route.params.campaignAddress}}
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
  name: 'InfoPage',
  data () {
    return {
      title: "Testing folder name as dynamic route"
    }
  }
}
</script>
