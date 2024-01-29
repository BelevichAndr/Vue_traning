<template>
  <div class="dialog" v-if="is_show" @click="$emit('update:is_show', false)">
    <div class="dialog__content" @click.stop>
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "my-dialog",
  props: {
    is_show: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style scoped>
.dialog {
  top: 0;
  bottom: 0;
  right: 0;
  left: 0;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  display: flex;
  align-items: center;
  justify-content: center;
}

.dialog__content {
  border-radius: 12px;
  min-height: 50px;
  min-width: 300px;
  padding: 20px;
}
</style>