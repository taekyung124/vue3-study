<template>
  <div>
    <div class="title">Tab 가이드</div>
  </div>
</template>
<script>
export default {
  name: 'TabGuide',
}
</script>
<style scoped>
.title {
  font-size: 30px;
  font-weight: bold;
  margin-bottom: 12px;
}
@media (max-width: 1024px) {
  .title {
    margin-top: 60px;
  }
}
</style>