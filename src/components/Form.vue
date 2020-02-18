<template>
  <div id="app">
    <el-form
      :model="ruleForm"
      :rules="rules"
      ref="ruleForm"
      label-width="100px"
      class="demo-ruleForm"
    >
      <el-form-item label="姓名" prop="name">
        <el-input v-model="ruleForm.name"></el-input>
      </el-form-item>

      <el-form-item label="系級/年級" prop="grade">
        <el-input v-model="ruleForm.grade"></el-input>
      </el-form-item>
      <el-form-item label="性別" prop="gender">
        <el-radio-group v-model="ruleForm.gender">
          <el-radio-button label="男"></el-radio-button>
          <el-radio-button label="女"></el-radio-button>
        </el-radio-group>
      </el-form-item>

      <!--
      <el-form-item label prop="privacy">
        <el-checkbox v-model="ruleForm.privacy">
          我同意
          <a href="#">隱私權條款</a>
        </el-checkbox>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" icon="el-icon-check" @click="submitForm('ruleForm',ruleForm)">送出</el-button>
      </el-form-item>
      
      -->
    </el-form>

    <qr-code :text="JSON.stringify(ruleForm)" style="align-content: center;"></qr-code>
    <!--
    {{ruleForm}}
    -->
  </div>
</template>

<script>
import Vue from "vue";
import VueQRCodeComponent from "vue-qrcode-component";
Vue.component("qr-code", VueQRCodeComponent);

export default {
  data() {
    return {
      ruleForm: {
        name: "",
        gender: "",
        grade: ""
        //privacy: false
      },
      rules: {
        name: [{ required: true, message: "請輸入姓名", trigger: "blur" }],
        gender: [{ required: true, message: "請選擇性別", trigger: "change" }],
        grade: [{ required: true, message: "請輸入系級/年級", trigger: "blur" }]
        /*
        privacy: [
          { required: true, message: "請同意隱私權條款", trigger: "blur" }
        ] 
        */
      }
    };
  },
  methods: {}
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  margin-right: 5%;
  margin-left: 5%;
}
</style>

// RegisterForm