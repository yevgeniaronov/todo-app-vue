<template>
  <div id="app">
    <b-container>
      <b-row class="justify-content-center">
        <b-col cols="12" md="6"><router-view /></b-col>
      </b-row>
    </b-container>
  </div>
</template>

<style lang="scss">
#app {
  font-family: Inter;
}

.trash-button {
  color: #cfd2d4;
  &:hover {
    color: #dc3545;
  }
}
</style>
