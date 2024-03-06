<template>
  <div>
    <div class="title">Select 가이드</div>
    <div class="sub-title">Select Type A</div>
    <SelectBox :optList="optListA" />
    <div class="sub-title">Select Type B</div>
    <SelectBox selType="SelectTypeB" :optList="optListB"></SelectBox>
    <div class="sub-title">Select Type C</div>
    <SelectBox selType="SelectTypeC" :optList="optListC" icoType="ico-type-sm"></SelectBox>
  </div>
</template>
<script>
import SelectBox from "./SelectBox.vue";

export default {
  name: 'SelectGuide',
  components: {
    'SelectBox' : SelectBox,
  },
  props: {

  },
  data() {
    return {
      selType: [
        'SelectTypeA',
        'SelectTypeB',
        'SelectTypeC',
      ],
      optListA: [
        { name: '옵션 A-1', value: '옵션 A-1'},
        { name: '옵션 A-2', value: '옵션 A-2'},
        { name: '옵션 A-3', value: '옵션 A-3'},
        { name: '옵션 A-4', value: '옵션 A-4'},
        { name: '옵션 A-5', value: '옵션 A-5'},
      ],
      optListB: [
        { name: '옵션 B-1', value: '옵션 B-1'},
        { name: '옵션 B-2', value: '옵션 B-2'},
        { name: '옵션 B-3', value: '옵션 B-3'},
        { name: '옵션 B-4', value: '옵션 B-4'},
        { name: '옵션 B-5', value: '옵션 B-5'},
      ],
      optListC: [
        { name: '옵션 C-1', value: '옵션 C-1'},
        { name: '옵션 C-2', value: '옵션 C-2'},
        { name: '옵션 C-3', value: '옵션 C-3'},
        { name: '옵션 C-4', value: '옵션 C-4'},
        { name: '옵션 C-5', value: '옵션 C-5'},
      ],
      icoType: [
        'ico-type-md',
        'ico-type-sm',
      ]
    }
  },
  computed: {

  },
  methods: {

  },
}
</script>
<style scoped>
.title {
  font-size: 30px;
  font-weight: bold;
  margin-bottom: 12px;
}
.sub-title {
  font-size: 18px;
  font-weight: bold;
  margin: 10px 0;
}
@media (max-width: 1024px) {
  .title {
    margin-top: 60px;
  }
}
</style>