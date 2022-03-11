<template>
  <div class="container">
    <div class="columns">
      <!-- Testing -->
      <div class="card-content">
        <div class="content">
          <NuxtLink to="/Campaign/campaignAddress/info">
            View Campaign at address - {{testCampaignAddress}}
          </NuxtLink>
        </div>
      </div>

      <!-- Testing dynamic routing in Nuxt -->
      <div class="card-content">
        <div class="content">
          <NuxtLink to="/User/456">
            View user at address - {{testUserAddress}}
          </NuxtLink>
        </div>
      </div>

      <!-- Testing for loop creation in Nuxt -->
      <div class="column">
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
    <div class="card-content">
      <div class="content">
        <b-button @click="connectToMetamask">Login</b-button>
        <h2>Account: <span class="showAccount"></span></h2>
      </div>
    </div>
  </div>
</template>

<script>
import Web3 from 'web3'

global.myWeb3 = new Web3(web3.currentProvider)

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
  mounted() {
    console.log(Web3.providers)
  },
  methods: {
    // Good reference
    async connectToMetamask () {
      if (typeof window.ethereum !== 'undefined') {

        // if (await myWeb3.eth.getAccounts()) {
        if (ethereum.selectedAddress) {
          alert('You are already logged in...')
        } else {
          let accounts = await ethereum.request({
            method: 'eth_requestAccounts'
          })
          console.log(accounts)
          this.getUserAccount()
        }
      } else {
        alert('INSTALL MM PLEASE')
      }
    },
    async getUserAccount() {
      const showAccount = document.querySelector('.showAccount');
      const accounts = await ethereum.request({ method: 'eth_requestAccounts' });
      const account = accounts[0];
      showAccount.innerHTML = account;
    }
  }
}
</script>
