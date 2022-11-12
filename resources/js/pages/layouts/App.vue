<template>
  <div>
    <header class="flex items-center space-x-2">
      <div class="flex-1"></div>
      <span>{{ auth.user.email }}</span>
      <button @click="logout">Log out</button>
    </header>
  </div>
</template>

<script>
import { Inertia } from '@inertiajs/inertia';

export default {
  props: {
    auth: { type: Object, required: true }
  },
  setup () {
    const logout = () => Inertia.post(route('logout'))

    return {
      logout
    }
  }
}
</script>