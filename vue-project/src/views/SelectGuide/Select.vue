<template>
  <div>
    <div class="title">Select 가이드</div>
    <div class="sub-title">Select Type A</div>
    <SelectBox :optList="optListA" :selectedText="defaultText" @getOptValue="clickedVal" @getOptIdx="clickedIdx"/>
    <div> index : {{ selectedIdxA }} / value : {{ selectedValA }} </div>
    <button @click="getSelectItemA">Select A Option Check</button>

    <div class="sub-title">Select Type B</div>
    <SelectBox selType="SelectTypeB" :optList="optListB" :selectedText="defaultTextB" @getOptValue="clickedVal" @getOptIdx="clickedIdx"/>
    <div> index : {{ selectedIdxB }} / value : {{ selectedValB }} </div>
    <button @click="getSelectItemB">Select B Option Check</button>

    <div class="sub-title">Select Type C</div>
    <SelectBox selType="SelectTypeC" :optList="optListC" icoType="ico-type-sm" :selectedText="defaultText" @getOptValue="clickedVal" @getOptIdx="clickedIdx"/>
    <div> index : {{ selectedIdxC }} / value : {{ selectedValC }} </div>
    <button @click="getSelectItemC">Select C Option Check</button>

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
      defaultText: '옵션을 선택해 주세요.',
      defaultTextB: '옵션 B-2',
      selectedValA: '선택 값 없음',
      selectedValB: 'B-2',
      selectedValC: '선택 값 없음',
      selectedIdxA: '선택 값 없음',
      selectedIdxB: '1',
      selectedIdxC: '선택 값 없음',
      selType: [
        'SelectTypeA',
        'SelectTypeB',
        'SelectTypeC',
      ],
      optListA: [
        { name: '옵션 A-1', value: 'A-1', type: 'A'},
        { name: '옵션 A-2', value: 'A-2', type: 'A'},
        { name: '옵션 A-3', value: 'A-3', type: 'A'},
        { name: '옵션 A-4', value: 'A-4', type: 'A'},
        { name: '옵션 A-5', value: 'A-5', type: 'A'},
      ],
      optListB: [
        { name: '옵션 B-1', value: 'B-1', type: 'B'},
        { name: '옵션 B-2', value: 'B-2', type: 'B'},
        { name: '옵션 B-3', value: 'B-3', type: 'B'},
        { name: '옵션 B-4', value: 'B-4', type: 'B'},
        { name: '옵션 B-5', value: 'B-5', type: 'B'},
      ],
      optListC: [
        { name: '옵션 C-1', value: 'C-1', type: 'C'},
        { name: '옵션 C-2', value: 'C-2', type: 'C'},
        { name: '옵션 C-3', value: 'C-3', type: 'C'},
        { name: '옵션 C-4', value: 'C-4', type: 'C'},
        { name: '옵션 C-5', value: 'C-5', type: 'C'},
      ],
      icoType: [
        'ico-type-md',
        'ico-type-sm',
      ],
    }
  },
  computed: {

  },
  methods: {
    clickedVal(type, value) {
      if( type === 'A' ) {
        this.selectedValA = value;
      } else if( type === 'B' ) {
        this.selectedValB = value;
      } else if( type === 'C' ) {
        this.selectedValC = value;
      }
    },
    clickedIdx(type, index) {
      if( type === 'A' ) {
        this.selectedIdxA = index;
      } else if( type === 'B' ) {
        this.selectedIdxB = index;
      } else if( type === 'C' ) {
        this.selectedIdxC = index;
      }
    },

    getSelectItemA(){
      alert('option index : ' + this.selectedIdxA + '/ option value : ' + this.selectedValA );
    },
    getSelectItemB(){
      alert('option index : ' + this.selectedIdxB + '/ option value : ' + this.selectedValB );
    },
    getSelectItemC(){
      alert('option index : ' + this.selectedIdxC + '/ option value : ' + this.selectedValC );
    },
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