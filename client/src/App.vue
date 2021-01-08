<template>
  <div id="appli">
    <ShellHeader />
    <router-view />
  </div>
</template>

<script>
import ShellHeader from './components/Shell/ShellHeader.vue';

export default {
  name: 'App',
  components: {
    ShellHeader
  }
};
</script>

<style lang="scss">
body {
  box-sizing: border-box;
  margin: 0;
}
#appli {
  max-width: 1920;
  display: flex;
  flex-direction: row;
}
</style>
