<template>
  <div class="notification-wrapper">
    <div
      class="notif-item"
      v-for="(item, key) in notificationItems"
      :key='key'
      @click="notificationItems.splice(key, 1)"
    >
      <p class="notif-msg">{{item}}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      notificationItems: []
    }
  },
  created() {
    this.$root.$on('notificationPush', (msg) => {
      this.notificationItems.push(msg)
    })
  }
}
</script>

<style lang="scss" scoped>
.notification-wrapper {
  @apply fixed;
  right: 2rem;
  bottom: 1rem;
  .notif-item {
    @apply border border-grey bg-white text-black shadow pl-4 pr-8 py-2 rounded relative;
    &:hover {
      @apply shadow-none;
      &::after {
        content: '×';
        right: 1rem;
        bottom: 0.5rem;
        @apply absolute text-grey-darker;
      }
    }
    &:not(:last-child) {
      @apply mb-2;
    }
    .notif-msg {

    }
  }
}
</style>
