<template>
  <div>
    <div class="title">Tab 가이드</div>
    <TabListButton></TabListButton>
    <TabContentBox></TabContentBox>
  </div>
</template>
<script>
import TabListButton from "@/views/TabGuide/TabListButton.vue";
import TabContentBox from "@/views/TabGuide/TabContentBox.vue";

export default {
  name: 'TabGuide',
  components: {
    TabListButton,
    TabContentBox,
  },

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