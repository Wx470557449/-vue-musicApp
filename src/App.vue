<template>
  <div id="app">
    <m-header></m-header>
    <tabs></tabs>
    <router-view></router-view>
  </div>
</template>

<script>
import MHeader from 'components/m-header/m-header'
import Tabs from 'components/tab/tab'
export default {
  components: {
    MHeader,
    Tabs
  }
}
</script>
<style lang="stylus"></style>
