<template>
  <section class="container block mx-auto my-10 px-4 text-black">
    <h1 class="font-light my-2">test notification</h1>
    <div class="form-wrap flex my-2">
      <input
        type="text"
        v-model="notificationText"
        class="w-4/5 px-4 py-2 rounded border border-grey mr-4"
      />
      <button
        class="w-1/5 bg-teal-light text-white shadow-sm px-4 py-2 rounded"
        @click="notificationPush"
      >show</button>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      notificationText: ''
    }
  },
  methods: {
    notificationPush() {
      this.$root.$emit('notificationPush', this.notificationText)
      this.notificationText = ''
    }
  }
}
</script>
