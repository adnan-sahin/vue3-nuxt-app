<script setup>
const route = useRoute();
const { data } = await useFetch("/api/ticker/?id=" + route.params.id);
const coin = data.value[0];
</script>
<template>
  <div>
    <h2>{{ coin.name }} Detail Page</h2>
    <table>
      <thead>
        <th>Symbol</th>
        <th>Rank</th>
        <th>Price -US $</th>
        <th>Market Cap - US $</th>
        <tr>
          <td>{{ coin.symbol }}</td>
          <td>{{ coin.rank }}</td>
          <td>{{ coin.price_usd }}</td>
          <td>{{ coin.market_cap_usd }}</td>
        </tr>
      </thead>
    </table>
  </div>
</template>
