<script>
import Modal from "./components/Modal.vue";
export default {
  data() {
    return {
      isShowModal: false,
    };
  },
  methods: {
    onTongleModal() {
      this.isShowModal = !this.isShowModal;
    },
  },
};
</script>

<template>
  <Teleport to="body">
    <Modal
      v-if="isShowModal"
      title="This is new title from app componemt"
      content="This is content modal"
      theme="contact"
      @cancle="onTongleModal"
    >
      <template v-slot:header>
        <h2>This is header</h2>
      </template>
      <template v-slot:footer>
        <button @click="onTongleModal">Cancle</button>
      </template>
      <label for="">Name </label>
      <input type="password" />
    </Modal>
  </Teleport>
  <button @click="onTongleModal">Tonggle modal</button>
</template>
