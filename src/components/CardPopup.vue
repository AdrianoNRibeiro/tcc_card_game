<!-- eslint-disable prettier/prettier -->
<template>
  <div class="popup-overlay" v-if="showPopup">
    <div class="popup-content">
      <h3>{{ currentCard.name }}</h3>
      <p>{{ currentCard.description }}</p>
      <button @click="hidePopup">Fechar</button>
    </div>
  </div>
</template>
<!-- eslint-disable prettier/prettier -->
<script>
export default {
  props: ["currentCard", "showPopup"],
  methods: {
    hidePopup() {
      this.$emit("hide-popup");
    },
  },
};
</script>
<!-- eslint-disable prettier/prettier -->
<style scoped>
.popup-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}

.popup-content {
  background-color: white;
  padding: 20px;
  border-radius: 5px;
}
</style>
