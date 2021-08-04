<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'MessageItem',
  props: {
    direction: String,
    message: String,
    photo: String,
  },
});
</script>

<style scoped>
.item-msg {
  display: flex;
}

.item-msg .box-img {
  width: 30px;
  height: 30px;
  border-radius: 100%;
  margin-right: 5px;
  overflow: hidden;
}

.item-msg img {
  width: 100%;
  height: 100%;
}

.item-msg .box-text {
  background-color: #fff;
  padding: 10px;
  color: #6c757d;
  font-size: 13px;
  border-radius: 10px;
}

.item-msg .time {
  color: #6c757d;
  font-size: 12px;
}

.toRight {
  flex-direction: row-reverse;
}

.toRight .box-text {
  background-color: #6610f2;
  color: #fff;
}

.toRight .box-img {
  margin-right: 0px;
  margin-left: 5px;
}

.toRight .time {
  text-align: right;
}
</style>

<template>
  <div class="d-flex item-msg mb-1" :class="direction">
    <div class="box-img mr-2">
      <img :src="require(`../assets/${photo}`)" />
      <span class="online"></span>
    </div>
    <div>
      <div class="box-text shadow-sm ">
        {{ message }}
      </div>
      <div class="time mt-1">9h atrás</div>
    </div>
  </div>
</template>
