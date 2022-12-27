<script setup>
const closeWindow = () => {
  window.close()
}
</script>

<template>
  <div class="header-img">
    <div class="title-bar"></div>
    <div @click="closeWindow()" class="close-button">
      <span>×</span>
    </div>
    <img src="../../src/assets/logo.png" alt="lazyeasyscalp" />
  </div>
</template>

<style scoped lang="scss">
.header-img {
  -webkit-user-select: none;
  -webkit-app-region: drag;
  aspect-ratio: 4 / 1;
  background-color: var(--color-primary);
  display: flex;
  justify-content: center;
  padding-top: 24px;

  .title-bar {
    height: 24px;
    width: 100%;
    position: absolute;
    top: 0;
    left: 0;
    background-color: var(--color-text);
  }

  .close-button {
    -webkit-app-region: no-drag;
    display: inline-flex;
    position: absolute;
    color: var(--color-background);
    top: 0px;
    right: 0px;
    justify-content: center;
    align-items: center;
    width: 30px;
    height: 24px;
    padding-top: 1px;
    font-size: 22px;
    z-index: 100;
    cursor: pointer;

    &:hover {
      color: var(--color-primary);
      z-index: 100;
    }
  }

  img {
    max-width: 100%;
    max-height: 100%;
    margin: auto;
  }
}
</style>
