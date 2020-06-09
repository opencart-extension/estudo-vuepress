<template>
  <div>
    <a
      v-for="social in $themeConfig.socialNetwork"
      :key="`social-network-${social.icon}`"
      :href="social.link"
      class="small-social"
    >
      <i :class="`${social.icon} big-icon-50 pix-slight-white`"></i>
    </a>
  </div>
</template>

<script>
export default {
  mounted() {
    console.log(this)
  }
}
</script>
