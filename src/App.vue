<template>
  <div id="app">
    <el-radio-group @change="change" v-model="radio1">
      <el-radio-button label="卡片"></el-radio-button>
      <el-radio-button label="列表"></el-radio-button>
    </el-radio-group>
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      radio1: "卡片"
    };
  },
  methods: {
    change(val) {
      if (val === "卡片") {
        this.$router.push("/");
      } else {
        this.$router.push("/List");
      }
    }
  }
};
</script>
