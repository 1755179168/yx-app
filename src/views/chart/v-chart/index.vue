<template>
  <div class="page-line-chart">
    <h4>用户操作</h4>
    <char :data="chartData" v-if="login"></char>
  </div>
</template>

<script>

import Veline from 'v-charts/lib/line.common';
import axios from 'axios';

export default {
  created() {
    axios.get('/api').then((r) => {
      this.chartData = r.data;
      this.login = true;
    });
  },
  components: {
    char: Veline,
  },
  data() {
    return {
      chartData: null,
      login: false,
    };
  },
};
</script>
