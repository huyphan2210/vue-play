<script setup lang="ts">
  import { ref } from 'vue'


</script>

<template>
  <header class="navigationBar">
    <div class="avatar">
        <img class="avatarImg" src="../../img/huy.jpeg">
    </div>
    <div class="navigation">

    </div>
    </header>
</template>

<style scoped>
  .navigationBar {
    display: flex;
    justify-content: space-between;
    position: fixed;
    width: 100%;
    height: var(--nav-bar-height);
    background-color: white;
  }
    .avatar {
        height: 100%;
    }
        .avatarImg {
            height: 100%;
        }
</style>
