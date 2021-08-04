<script lang="ts">
import { defineComponent } from 'vue';
import ListUsers from './ListUsers.vue';

export default defineComponent({
  name: 'ChatHeader',
  components: {},
  // props: {},
});
</script>

<style scoped>
.header {
  display: flex;
  align-items: center;
  padding: 15px 15px;
  height: 55px;
}
</style>

<template>
  <div class="header shadow-sm">
    <div class="d-flex align-tems-center flex-grow-1">
      <div class="user-img mr-2">
        <img src="../assets/user2.jpg" />
        <span class="online"></span>
      </div>

      <div class="flex-grow-1">
        <article>Ana José</article>
        <small class="text-muted">Aproveite o melhor da vida! ✌🙏💋</small>
      </div>
    </div>
    <div>
      <div class="icon-actions">
        <a href="#"><i class="feather-phone"></i></a>
        <a href="#"><i class="feather-video"></i></a>
      </div>
    </div>
  </div>
</template>
