<!-- https://juejin.im/post/5b03e610f265da0b873ad64e -->
<template>
  <div class="select">
    <div class="inner">
      <div class="innerWrapper" @click="showOptions = !showOptions">
        <input type="text" readonly placeholder="请选择菜品" :value="selectedItem">
        <span class="dropdown"></span>
      </div>
      <ul class="options" v-show="showOptions" v-clickOut="test">
        <li v-for="(item, index) in options" :key="index" @click.stop="choose(item.value)">{{item.value}}</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selectedItem: '',
      showOptions: false,
      options: [
        {
          value: '西红柿炒鸡蛋'
        },
        {
          value: '青椒炒鸡蛋'
        },
        {
          value: '回锅肉撒'
        },
        {
          value: '宫保鸡丁'
        },
        {
          value: '肉香肉丝'
        }
      ]
    };
  },
  methods: {
    choose(selected) {
      this.selectedItem = selected;
      this.showOptions = false;
    },
    test() {
      // console.log('This is a test function invoked by custom directive');
      this.showOptions = false;
    }
  },
  // mounted() {
  //   let that = this;
  //   document.addEventListener('click', function() {
  //     that.showOptions = false;
  //   });
  // }
  directives: {
    clickOut: {
      bind: function(el, binding) {
        // console.log('el =>=>=>=>=>=>=>', el);
        // console.log('binding.name =>=>=>=>=>', binding.name);
        // console.log('binding.expression =>=>=>=>=>', binding.expression);
        // console.log('binding.value =>=>=>=>=>', binding.value);
        document.addEventListener('click', function(e) {
          if (el.contains(e.target)) return false;
          if (binding.expression) {
            binding.value();
          }
        });
      }
      // unbind: function(el) {}
    }
  }
};
</script>



<style lang="scss" scoped>
$size: 14px;
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
.ul,
ol,
li {
  list-style: none;
}
.inner {
  position: relative;
  margin: 0 auto;
  width: 200px;
  height: 30px;
  font-size: $size;
  border: 1px solid #dddee1;
  border-radius: 3px;
  .inputWrapper {
    width: 100%;
    height: 100%;
    > input {
      width: 85%;
      height: 100%;
      padding-left: 10px;
      border: none;
      cursor: pointer;
    }
  }
  > .options {
    text-align: left;
    position: absolute;
    left: 0;
    right: 0;
    top: 120%;
    padding: 10px 0;
    background-color: #fff;
    box-shadow: 0 0 4px #ddd;
    border-radius: 3px;
    overflow: auto;
    > li {
      padding: 3px 10px;
      cursor: pointer;
      &:hover {
        background-color: #eee;
      }
    }
  }
}
</style>
