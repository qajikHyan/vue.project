<template>
  <div class="empty-layout bg-img">
    <router-view/>
  </div>
</template>

<script>
import messages from '@/utils/messages'

export default {
  computed: {
    error() {
      return this.$store.getters.error
    }
  },
  watch: {
    error(fbError) {
      this.$error(messages[fbError.code] || 'Что-то пошло не так')
    }
  }
}
</script>

<style>
  .bg-img{
    background-image: url(../assets/images/background.jpg);
    background-size: 100%;
    background-position: bottom;
  }
</style>
