<template>
  <div id="app">
    
    <ApiNoticias id="noticias"></ApiNoticias>
    <TeamCard id="team"></TeamCard>

  </div>
</template>

<script>
import TeamCard from "./components/TeamCard.vue"
import ApiNoticias from "./components/ApiNoticias.vue"

export default {
  name: 'App',
  components: {
    TeamCard,
    ApiNoticias
  }
}
</script>

