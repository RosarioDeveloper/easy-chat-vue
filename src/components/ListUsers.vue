<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'ListUsers',
  props: {
    name: String,
    photo: String,
    active: Boolean,
    online: Boolean,
  },
});
</script>

<style scoped>
.users {
  padding: 10px 20px;
  cursor: pointer;
  transition: all 0.4s;
  -webkit-transition: all 0.4s;
  -moz-transition: all 0.4s;
}

.users.active {
  background-color: rgb(221, 221, 221);
}

.numMsg {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #6610f2;
  width: 15px;
  height: 15px;
  color: #fff;
  padding: 3px;
  font-size: 11px !important;
}
.numMsg.view {
  background-color: #9d9e9e;
}
</style>

<template>
  <div class="d-flex users" :class="{ active: active }">
    <div class="user-img mr-2">
      <img :src="require(`../assets/${photo}`)" />
      <span :class="{ online: online, offline: !online }"></span>
    </div>

    <div class="flex-grow-1">
      {{ name }}<br />
      <small>Ter - 09:30</small>
    </div>

    <div v-if="!active">
      <div class="numMsg rounded-circle">4</div>
    </div>
  </div>
</template>
