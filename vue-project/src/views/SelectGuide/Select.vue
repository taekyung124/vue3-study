<template>
  <div>
    <div class="title">Select 가이드</div>
    <div class="sub-title">Select Type A</div>
    <SelectBox ref="getItem" :optList="optListA" :selectedText="defaultText" @getOpt="clickedOptA" />
    <div> {{ selectedA }} </div>
    <button @click="getSelectItemA">Select A Option Check</button>

    <div class="sub-title">Select Type B</div>
    <SelectBox ref="getItem" selType="SelectTypeB" :optList="optListB" :selectedText="defaultText" @getOpt="clickedOptB" />
    <div> {{ selectedB }} </div>
    <button @click="getSelectItemB">Select B Option Check</button>

    <div class="sub-title">Select Type C</div>
    <SelectBox ref="getItem" selType="SelectTypeC" :optList="optListC" icoType="ico-type-sm" :selectedText="defaultText" @getOpt="clickedOptC" />
    <div>  {{ selectedC }} </div>
    <button @click="getSelectItemC">Select C Option Check</button>

  </div>
</template>
<script setup>
import { ref, onMounted } from "vue";

const getItem = ref(null);

onMounted(() => {
  this.$refs.onClickItem()
})
</script>

<script>
import SelectBox from "./SelectBox.vue";

export default {
  name: 'SelectGuide',
  components: {
    'SelectBox' : SelectBox,
  },
  data() {
    return {
      defaultText: '',
      selectedA: undefined,
      selectedB: undefined,
      selectedC: undefined,
      selType: [
        'SelectTypeA',
        'SelectTypeB',
        'SelectTypeC',
      ],
      optListA: [
        { name: '옵션 A-1', value: 'A-1',},
        { name: '옵션 A-2', value: 'A-2',},
        { name: '옵션 A-3', value: 'A-3',},
        { name: '옵션 A-4', value: 'A-4',},
        { name: '옵션 A-5', value: 'A-5',},
      ],
      optListB: [
        { name: '옵션 B-1', value: 'B-1',},
        { name: '옵션 B-2', value: 'B-2',},
        { name: '옵션 B-3', value: 'B-3',},
        { name: '옵션 B-4', value: 'B-4',},
        { name: '옵션 B-5', value: 'B-5',},
      ],
      optListC: [
        { name: '옵션 C-1', value: 'C-1',},
        { name: '옵션 C-2', value: 'C-2',},
        { name: '옵션 C-3', value: 'C-3',},
        { name: '옵션 C-4', value: 'C-4',},
        { name: '옵션 C-5', value: 'C-5',},
      ],
      icoType: [
        'ico-type-md',
        'ico-type-sm',
      ],
      getSelectItemA: null,
      getSelectItemB: null,
      getSelectItemC: null,
    }
  },
  computed: {

  },
  methods: {

    // 선택된 옵션 데이터 메서드
    clickedOptA(value,index) {
      this.selectedA = 'index : ' + index + ' / value : ' + value;
    },
    clickedOptB(value,index) {
      this.selectedB = 'index : ' + index + ' / value : ' + value;
    },
    clickedOptC(value,index) {
      this.selectedC = 'index : ' + index + ' / value : ' + value;
    },

    // alert 호출 메서드

    getSelectItemB(value,index){
      alert('선택 된 옵션 DATA :' + 'index : ' + index + ' / value : ' + value);
    },
    getSelectItemC(value,index){
      alert('선택 된 옵션 DATA :' + 'index : ' + index + ' / value : ' + value);
    },
  },
  mounted() {
    // console.log(this.$refs.SelectedItemA.$refs.SelectItem.value);
    // console.log(this.$refs.SelectedItemB.$refs.SelectItem.value);
    // console.log(this.$refs.SelectedItemC.$refs.SelectItem.value);
  }
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
button { margin-top: 4px;}
@media (max-width: 1024px) {
  .title {
    margin-top: 60px;
  }
}
</style>