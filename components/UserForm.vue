<script lang="ts" setup>
import type { User } from '~/app.vue'

const emit = defineEmits<{
  (e: 'submit', value: User): void
}>()

const model = defineModel<User>({
  default: {
    name: '',
    email: '',
    phone: '',
  },
})
</script>

<template>
  <form @submit.prevent="emit('submit', model)">
    <div
      class="form-group"
    >
      <label for="name">Name</label>
      <input id="name" v-model="model.name" type="text">
    </div>
    <div class="form-group">
      <label for="email">Email</label>
      <input id="email" :value="model.email" type="email">
    </div>
    <div class="form-group">
      <label for="phone">Phone</label>
      <input id="phone" :value="model.phone" type="text">
    </div>
    <button type="submit">
      Submit
    </button>
  </form>
</template>
