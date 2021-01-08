<template>
  <nav class="shell-menu">
    <slot></slot>
  </nav>
</template>
_
<script>
export default {
  name: 'ShellMenu'
};
</script>

<style>
.shell-menu {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-content: space-between;
  margin-top: 100px;
}
</style>
