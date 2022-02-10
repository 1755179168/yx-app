<template>
  <div>
    <span class="p">商品种类：</span>
    <a-select :default-value="'选择分类'" style="width: 200px" @change="handleChange">
        <!--  -->
        <!--  -->
        <a-select-option :value="prop" v-for="prop in option" :key="prop"> {{prop}}
           </a-select-option>
           <a-select-option value="不选择">不选择</a-select-option>
    </a-select>
    <a-button type="primary" class="b" @click="btnClick"> login </a-button>
  </div>
</template>
<script>
export default {
  props: {
    option: {
      type: Array,
      default: () => [],
    },
  },
  methods: {
    handleChange(value) {
      // console.log(`selected ${value}`);
      this.value = value;
    },
    btnClick() {
      if (this.value === '不选择') {
        this.value = false;
      }
      this.$emit('btnClick', this.value);
    },
  },
  data() {
    return {
      value: '',
    };
  },
};
</script>
<style lang="less" scoped>
span.p {
  margin: 0 0 0 20px;
}
.b {
  margin: 0 20px;
}
</style>
