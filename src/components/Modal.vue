<template>
  <div class="backdrop">
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <slot>Default Content</slot>
      <!-- <h1>{{ header }}</h1>
      <p>{{ text }}</p> -->
      <div class="actions">
        <slot name="links"></slot>
      </div>
      <button class="btn" @click="closeModal">Close Modal</button>
    </div>
  </div>
</template>

<script>
export default {
  props: ['header', 'text', 'theme'],
  methods: {
    closeModal() {
      this.$emit('close')
    }
  }
}
</script>

<style>
  .modal {
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: white;
    border-radius: 10px;
  }
  .backdrop {
    top: 0;
    position: fixed;
    background: rgba(0,0,0,0.5);
    width: 100%;
    height: 100%;
  }
  .modal h1 {
    color: rgb(22, 99, 22);
    border: none;
    padding: 0;
  }
  .modal.sale {
    background: rgb(165, 12, 43);
    color: white;
  }
  .modal.sale h1 {
    color: white;
  }
  button.btn {
    padding: 10px 20px;
    background-color: #090916;
    color: white;
    border-radius: 20px;
    border: 1px solid #090916;
    margin-top: 20px;
}
</style>