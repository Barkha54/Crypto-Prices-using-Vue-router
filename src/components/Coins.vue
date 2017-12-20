<template>
  <div>
    <p>Name: {{ coin.name }}</p>
    <p>Symbol: {{ coin.symbol }}</p>
    <p>Price (USD): {{ coin.price_usd }}</p>
    <p>Rank: {{coin.rank}}</p>
    <p>Market Cap used: {{coin.market_cap_usd}}</p>
    <p>Price (BTC): {{coin.price_btc}}</p>
    <p>Total Supply: {{coin.total_supply}}</p>
    <p>Maximum Supply: {{coin.max_supply}}</p>
    <p>Percent Change since 1 hr: {{coin.percent_change_1h}}</p>
    <p>Percent change since 24 hr: {{coin.percent_change_24h}}</p>
    <p>Percent Change since 7 days: {{coin.percent_change_7d}}</p>
    <p>Last Updated: {{coin.last_updated}}</p>
  </div>
</template>
<script>
  import axios from 'axios'

  export default {
    name: 'Coins',

    data() {
      return {
        coin: {}
      }
    },

    created() {
      this.fetchData()
    },

    watch: {
      '$route': 'fetchData'
    },

    methods: {
      fetchData() {
        axios.get('https://api.coinmarketcap.com/v1/ticker/'+this.$route.params.id+'/')
        .then((resp) => {
          this.coin = resp.data[0]
          console.log(resp)
        })
        .catch((err) => {
          console.log(err)
        })
      }
    }
  }
</script>