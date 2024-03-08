<template>
  <div>
    <div class="title">Select 가이드</div>
    <div class="sub-title">Select Type A</div>
    <SelectBox ref="getItem" :optList="optListA" :selectedText="defaultText" @getOpt="clickedOptA" />
    <div> {{ selectedResultA }} </div>
    <button @setAlert="getClickedItemA">Select A Option Check</button>

    <div class="sub-title">Select Type B</div>
    <SelectBox ref="getItem" selType="SelectTypeB" :optList="optListB" :selectedText="defaultText" @getOpt="clickedOptB" />
    <div> {{ selectedResultB }} </div>
    <button @setAlert="getClickedItemB">Select B Option Check</button>

    <div class="sub-title">Select Type C</div>
    <SelectBox ref="getItem" selType="SelectTypeC" :optList="optListC" icoType="ico-type-sm" :selectedText="defaultText" @getOpt="clickedOptC" />
    <div>  {{ selectedResultC }} </div>
    <button @setAlert="getClickedItemC">Select C Option Check</button>

  </div>
</template>
<script setup>
/*import { ref, onMounted } from "vue";

const getItem = ref(null);

onMounted(() => {
  this.;
})*/
</script>

<script>
import SelectBox from "./SelectBox.vue";
import { provide } from "vue";

export default {
  name: 'SelectGuide',
  components: {
    'SelectBox' : SelectBox,
  },
  data() {
    return {
      // 셀렉트 타입 A,B,C
      selType: [
        'SelectTypeA',
        'SelectTypeB',
        'SelectTypeC',
      ],
      // 옵션 리스트 배열
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
      // 아이콘 타입 배열
      icoType: [
        'ico-type-md',
        'ico-type-sm',
      ],
      // placeholder 초기 값
      defaultText: '',
      // 선택된 옵션의 인덱스, 밸류 값
      selectedResultA: undefined,
      selectedResultB: undefined,
      selectedResultC: undefined,
      // selected 된 옵션이 있을 경우
      selectedOptData: undefined,
      alertMessage: undefined,
    }
  },
  computed: {

  },
  methods: {

    // 선택된 옵션 데이터 메서드
    clickedOptA(value,index) {
      this.selectedResultA = 'index : ' + index + ' / value : ' + value;
    },
    clickedOptB(value,index) {
      this.selectedResultB = 'index : ' + index + ' / value : ' + value;
    },
    clickedOptC(value,index) {
      this.selectedResultC = 'index : ' + index + ' / value : ' + value;
    },

    // alert 호출 메서드
    getClickedItemA(value,index) {
      this.alertMessage = `선택 된 옵션 DATA - ${index} : index / value : ${value}`;
      alert( this.alertMessage );
      console.log(this.alertMessage);
    },
    getClickedItemB(value,index) {
      this.alertMessage = `선택 된 옵션 DATA - ${index} : index / value : ${value}`;
      alert( this.alertMessage );
      console.log(this.alertMessage);
    },
    getClickedItemC(value,index){
      this.alertMessage = `선택 된 옵션 DATA - ${index} : index / value : ${value}`;
      alert( this.alertMessage );
      console.log(this.alertMessage);
    },

  },
  mounted() {

  },
  setup() {
    provide('key','value');
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
button { margin-top: 4px;}
@media (max-width: 1024px) {
  .title {
    margin-top: 60px;
  }
}
</style>