<template>
  <div class="ui-select" :class="$props.selType" :style="selTypeStyle">
    <div class="ui-select-box" :style="isActiveStyle">
      <button class="ui-select-menu-btn" @click="onClickShow">
        <i :class="icoType" :style="ArwStyle"></i>
        <span class="ui-select-menu-text">{{selectedText}}</span>
      </button>
    </div>
    <div class="ui-select-menu-wrap" v-if="MenuWrapShow" :style="ComputedTop">
      <ul class="ui-select-menu-list" :style="BorderStyle">
        <li class="ui-select-menu-item" :style="OptListStyle"
            v-for="(optData, index) in $props.optList" :key="index" :value="optData.value"
            @click="onClickItem(optData)"
        >
          {{ optData.name }}
        </li>
      </ul>
    </div>
  </div>
</template>
<script>
export default {
  name: 'SelectBox',
  data() {
    return {
      selectedText: '옵션 선택',
      MenuWrapShow: false,
    }
  },
  props: {
    selType: {
      type: String,
      default: 'SelectTypeA',
    },
    optList: {
      type: Array,
      default: [],
    },
    icoType: {
      type: String,
      default: 'ico-type-md',
    },
  },
  computed: {
    selTypeStyle () {
      if (this.$props.selType === 'SelectTypeA') {
        return {
          width: '450px',
          height: '44px',
        }
      }
      if (this.$props.selType === 'SelectTypeB') {
        return {
          width: '120px',
          height: '38px'
        }
      }
      if (this.$props.selType === 'SelectTypeC') {
        return {
          display: 'inline-block',
          width: 'auto',
          height: '19px',
          marginRight: '23px',
          fontSize: '13px',
          lineHeight: '19px',
        }
      }
    },
    isActiveStyle () { // 옵션 리스트 노출 여부에 따라 select-box 스타일 수정
      if(this.$props.selType !== 'SelectTypeC') {
        if( this.MenuWrapShow ) {
          return {
            border: '1px solid black',
            borderBottom: '0',
            borderRadius: '6px 6px 0 0',
          }
        } else {
          return {
            border: '1px solid #d5d5d5',
            borderRadius: '6px',
          }
        }
      } else {
        return {
          border: '0',
        }
      }
    },
    ArwStyle () { // 옵션 리스트 노출 여부에 따라 아이콘 스타일 수정
      if( this.MenuWrapShow ) {
        return {
          transform: 'rotate(180deg)',
        }
      } else {
        return {
          transform: 'rotate(0)',
        }
      }
    },
    ComputedTop () { // ui-select-menu-wrap 스타일 수정
      if (this.$props.selType === 'SelectTypeA') {
        return {
          top: '44px',
        }
      }
      if (this.$props.selType === 'SelectTypeB') {
        return {
          top: '38px',
        }
      }
      if (this.$props.selType === 'SelectTypeC') {
        return {
          top: '23px',
          left: '0',
          width: '103px',
        }
      }
    },
    BorderStyle () {
      if(this.$props.selType !== 'SelectTypeC') {
        return {
          borderRadius: '0 0 6px 6px'
        }
      } else {
        return {
          borderRadius: '6px'
        }
      }
    },
    OptListStyle () {
      if(this.$props.selType !== 'SelectTypeC') {
        return {
          position: 'relative',
          width: '100%',
          padding: '11px 14px',
          fontSize: '14px',
          lineHeight: '22px',
          cursor: 'pointer',
          transition: 'background-color 0.2s ease-out',
        }
      } else {
        return {
          padding: '12px',
        }
      }
    },
  },
  methods: {
    onClickShow: function (e) {
      e.preventDefault();
      this.MenuWrapShow = !this.MenuWrapShow;
    },
    onClickItem(optData) {
      this.MenuWrapShow = false;
      this.selectedText = optData.name;
    },
  },
  mounted() {

  },
}
</script>
<style scoped lang="css">
* {
  position: relative;
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  text-align: left;
}
button {
  background: transparent;
  padding: 0;
  border: 0;
}
.ui-select {
  position: relative;
  background: #fff;
}
.ui-select-box {
  height: 100%;
  transition: border-color 0.2s ease-out, border-radius 0.2s ease-out;
}
.ui-select-menu-btn {
  position: relative;
  width: 100%;
  height: 100%;
  padding: 0 14px;
  background: transparent;
  text-align: left;
}
.SelectTypeC .ui-select-menu-btn {
  padding: 0;
}
/* 아이콘 타입 */
.ico-type-md {
  position: absolute;
  top: 15px;
  right: 14px;
  width: 9px;
  height: 8px;
  background: no-repeat center/9px 8px url("../../components/images/arw_select@2x.png");
  transform: rotate(0);
  transition: transform 0.2s ease-out;
}
.SelectTypeA .ico-type-md{
  top: 17px;
}
.ico-type-sm {
  position: absolute;
  top: 2px;
  right: -23px;
  width: 19px;
  height: 19px;
  border: 1px solid #d5d5d5;
  border-radius: 50%;
  background: no-repeat center/7px 4px url("../../components/images/arw_select_sm@2x.png");
  transform: rotate(0);
  transition: transform 0.2s ease-out;
}
.ui-select-menu-wrap {
  position: absolute;
  z-index: 10;
  left: 0;
  width: 100%;
  background-color: white;
}
.SelectTypeC .ui-select-menu-wrap .ui-select-menu-list .ui-select-menu-item {
  padding: 12px;
}
.ui-select-menu-list {
  border: 1px solid black;
  list-style: none;
}
.ui-select-menu-item:hover {
  background-color: #f5f5f5;
}
</style>