<template>
  <aside class="shell-header" :class="{ short: isShort, large: !isShort }">
    <div
      class="shell-header__hamburger"
      v-if="isShort"
      @click="isShort = false"
    >
      &#x2630;
    </div>
    <div class="shell-header__large" v-else>
      <div class="shell-header__logo">
        <router-link to="/">
          <img src="/shell/logo.png" alt="Bug Tracker" width="48" height="48" />
        </router-link>
        <p class="shell-header__logo-text">Ade Bug Tracker</p>
      </div>
      <ShellMenu>
        <ShellItem
          pathTo="/about"
          text="Report a bug"
          imgSrc="/shell/homepage.svg"
        />
        <ShellItem
          pathTo="/"
          text="Report a bug"
          imgSrc="/shell/homepage.svg"
        />
        <ShellItem
          pathTo="/"
          text="Report a bug"
          imgSrc="/shell/homepage.svg"
        />
        <ShellItem
          pathTo="/"
          text="Report a bug"
          imgSrc="/shell/homepage.svg"
        />
        <ShellItem
          pathTo="/"
          text="Report a bug"
          imgSrc="/shell/homepage.svg"
        />
      </ShellMenu>
      <button @click="isShort = true" class="shell-header__button">
        <p>&#8592;</p>
        <p>Collapse Menu</p>
      </button>
    </div>
  </aside>
</template>

<script>
import ShellMenu from './ShellMenu.vue';
import ShellItem from './ShellItem.vue';

export default {
  name: 'ShellHeader',
  components: {
    ShellMenu,
    ShellItem
  },
  data() {
    return { isShort: false };
  }
};
</script>

<style lang="scss" scoped>
.short {
  width: 5%;
  transition: width 1s ease;
}

.large {
  width: 15%;
  transition: width 1s ease;
}

.shell-header {
  // display: flex;
  // flex-direction: column;
  background: lightcoral;
  min-height: 100vh;

  .shell-header__hamburger {
    font-size: 2rem;
    text-align: center;
  }

  .shell-header__large {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    background: lightcoral;
    min-height: 100%;
  }

  .shell-header__logo {
    display: flex;
    align-items: center;
    margin-top: 20px;
    font-size: 15px;

    p {
      margin-left: 15px;
    }
  }

  .shell-header__button {
    margin-top: auto;
    margin-bottom: 0;
    // padding: 20px 0;
    border: none;
    border-top: 1px solid grey;
    display: flex;
    justify-content: space-between;
    cursor: pointer;
    background: grey;
  }
}
</style>
