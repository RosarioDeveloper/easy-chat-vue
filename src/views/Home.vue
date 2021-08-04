<script lang="ts">
import { defineComponent } from 'vue';
import ChatHeader from '../components/ChatHeader.vue';
import ListUsers from '../components/ListUsers.vue';
import MessageItem from '../components/MessageItem.vue';

export default defineComponent({
  name: 'Home',
  components: { MessageItem, ListUsers, ChatHeader },
  setup() {
    const msg = [
      { photo: 'user2.jpg', dir: '', msg: 'Olá Rosário!!' },
      { photo: 'user1.jpg', dir: 'toRight', msg: 'Oi tudo bem contigo?' },
      { photo: 'user2.jpg', dir: '', msg: 'Tudo e contigo?' },
      { photo: 'user1.jpg', dir: 'toRight', msg: 'Também' },
      {
        photo: 'user1.jpg',
        dir: 'toRight',
        msg: 'Falaste com a Ana sobre aquele assunto?',
      },
      { photo: 'user2.jpg', dir: '', msg: 'Sim falei com ela' },
      { photo: 'user2.jpg', dir: '', msg: 'Ela disse que não estava disponível' },
      { photo: 'user1.jpg', dir: 'toRight', msg: 'Ok, obrigado pelo tempo' },
    ];

    const users = [
      {
        name: 'João Amadeu',
        photo: 'user5.jpg',
        active: false,
        online: true,
      },
      {
        name: 'Ana josé',
        photo: 'user2.jpg',
        active: true,
        online: true,
      },

      {
        name: 'Bruno Samora',
        photo: 'user4.jpg',
        active: false,
        online: false,
      },
      {
        name: 'Joana Machado',
        photo: 'user3.jpg',
        active: false,
        online: true,
      },
    ];

    return {
      msg,
      users,
    };
  },
});
</script>

<template>
  <div class="row content d-flex justify-content-center">
    <div class="col-lg-2 p-0" style="background-color: #ebebeb">
      <div class="logo shadow-sm mb-2">
        <i class="feather-message-circle mr-2"></i> <span>EasyChat</span>
      </div>

      <span class="px-3">Conversas Recentes</span>
      <div v-for="item in users" :key="item">
        <ListUsers
          :name="item.name"
          :photo="item.photo"
          :active="item.active"
          :online="item.online"
        />
      </div>
    </div>

    <div class="col-lg-6 col-12 chat-content bg-light shadow-sm">
      <ChatHeader />

      <div class="chat-item flex-grow-1">
        <div v-for="item in msg" :key="item">
          <MessageItem :photo="item.photo" :message="item.msg" :direction="item.dir" />
        </div>
      </div>

      <div class="box-actions d-flex align-items-center">
        <div class="icon-actions">
          <a href="#"><i class="feather-camera"></i></a>
          <a href="#"><i class="feather-image"></i></a>
          <a href="#"><i class="feather-mic"></i></a>
        </div>

        <div class="chat-form flex-grow-1">
          <div class="d-flex align-items-center">
            <div class="ml-3 flex-grow-1">
              <input type="text" class="rounded-pill" placeholder="Digite uma mensagem" />
            </div>

            <div class="form-icons">
              <i>☻</i>

              <!-- <i class="feather-alert-circle"></i>
              <i class="feather-paperclip"></i> -->
            </div>
          </div>
        </div>

        <!-- <div>
          <button class="btn btn-sm btn-primary ">Enviar </button>
        </div> -->
      </div>
    </div>
  </div>
</template>
