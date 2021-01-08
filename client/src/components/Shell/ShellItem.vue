<template>
  <div class="shell-item">
    <router-link :to="pathTo" class="shell-item__link">
      <div class="shell-item__wrapper">
        <img
          :src="imgSrc"
          alt=""
          class="shell-item__img"
          width="32"
          height="32"
        />
        <p>{{ text }}</p>
      </div>
      <p class="shell-item__icon">&#10140;</p>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'ShellItem',
  props: {
    text: String,
    imgSrc: String,
    pathTo: String
  }
};
</script>

<style lang="scss" scoped>
.shell-item__link {
  display: flex;
  justify-content: space-around;
  align-items: center;
  width: 100%;
  background: red;
  font-size: 1.2rem;
  cursor: pointer;

  .shell-item__wrapper {
    display: flex;
    align-items: center;
    width: 90%;

    p {
      margin-left: 10px;
    }
  }
}
</style>
