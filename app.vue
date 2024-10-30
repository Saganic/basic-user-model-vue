<script lang="ts" setup>
export interface User {
  name: string
  email: string
  phone: string
}

const user1 = ref<User>(initUser())

const user2 = ref<User>(initUser())

function initUser() {
  return {
    name: '',
    email: '',
    phone: '',
  }
}
</script>

<template>
  <div>
    <div style="border: 1px solid grey; padding: 4px">
      <p>User 1</p>
      <UserForm
        v-model="user1"
      />
      {{ user1 }}
    </div>

    <div style="border: 1px solid grey; padding: 4px">
      <p>User 2</p>
      <UserForm
        v-model="user2"
      />
      {{ user2 }}
    </div>

    <div style="border: 1px solid grey; padding: 4px">
      <button @click="user1 = initUser()">
        Reset user1
      </button>
      <button @click="user2 = initUser()">
        Reset user2
      </button>
    </div>
  </div>
</template>
