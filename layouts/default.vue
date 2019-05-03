<template>
  <div class="font-sans">
    <nuxt />
    <notification />
  </div>
</template>
<script>
import notificationTemplate from '@/components/notificationTemplate.vue'
export default {
  components: {
    'notification': notificationTemplate
  }
}
</script>
