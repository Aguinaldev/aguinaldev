<template>
  <div>
    <Header></Header>
    <Card></Card>
    <Footer></Footer>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Header from '~/components/Header.vue'
import Card from '~/components/Card.vue'
import Footer from '~/components/Footer.vue'

export default Vue.extend({
    name: "IndexPage",
    components: { Header, Card, Footer }
})
</script>
