<template>
  <div>
    <h1>Home Page</h1>
    <!--Testing -->
    <div>
      <NuxtLink to="/Campaign/campaignAddress/info">
        View Campaign at address - {{testCampaignAddress}}
      </NuxtLink>
    </div>
    <!--Testing dynamic routing in Nuxt-->
    <div>
      <NuxtLink to="/User/456">
        View user at address - {{testUserAddress}}
      </NuxtLink>
    </div>
    <!--Testing for loop creation in Nuxt-->
    <div>
        <p>
          Testing for loop for creating nuxtlinks
        </p>
        <div v-for="userAddress in testUserAddressList">
          <NuxtLink :to="`/User/${userAddress}`">
            Link to User {{userAddress}}
          </NuxtLink>
        </div>
    </div>

  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data () {
    return {
      testCampaignAddress: 123,
      testUserAddressList: [
        1, 2, 3, 4, 5, 6
      ],
      testUserAddress: 456
    }
  },
  methods: {
    getCurrentUserAddress () {

    }
  }
}
</script>
