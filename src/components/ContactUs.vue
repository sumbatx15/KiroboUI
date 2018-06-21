<template>
  <el-form :model="ruleForm" :rules="rules" ref="ruleForm" label-width="120px" class="demo-ruleForm">
    <div class="contact-us-fields">
      <el-form-item prop="name">
        <el-input v-model="ruleForm.name" placeholder="Your name"></el-input>
      </el-form-item>
      <el-form-item prop="mail">
        <el-input v-model="ruleForm.mail" placeholder="Your mail"></el-input>
      </el-form-item>
    </div>
    <div class="contact-us-fields">
      <el-form-item prop="message">
        <el-input v-model="ruleForm.message" placeholder="Your message"></el-input>
      </el-form-item>
      <el-form-item>
        <div class="contact-us-submit-button" @click="submitForm('ruleForm')">SUBMIT</div>
      </el-form-item>
    </div>

  </el-form>
</template>

<script>
export default {
  data() {
    return {
      ruleForm: {
        name: "",
        mail: "",
        message: ""
      },
      rules: {
        name: [
          {
            required: true,
            message: "Please input name",
            trigger: "blur"
          }
        ],
        mail: [
          {
            required: true,
            message: "Please input mail",
            trigger: "blur"
          }
        ],
        message: [
          {
            required: true,
            message: "Please input mail",
            trigger: "blur"
          }
        ]
      }
    };
  },
  methods: {
    submitForm(formName) {
      this.$refs[formName].validate(valid => {
        if (valid) {
          this.$message({
            message: "Thank you.",
            type: "success"
          });
          this.ruleForm = {
            name: "",
            mail: "",
            message: ""
          };
        } else {
          console.log("error submit!!");
          return false;
        }
      });
    },
    resetForm(formName) {
      this.$refs[formName].resetFields();
    }
  }
};
</script>

<style>
.el-form-item__content {
  margin-left: 0 !important;
}
.el-input__inner {
  border-radius: 50px !important;
  height: 50px !important;
}
.contact-us-fields {
  display: flex;
}
.contact-us-fields > :first-child {
  margin-right: 20px;
}
.contact-us-submit-button {
  cursor: pointer;
  height: 50px !important;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  flex: 1 1 50%;
  background: #171e2e;
  border-radius: 100px;
  border: 2px solid #47cbff;
  color: #47cbff;
  font-weight: bold;
  width: 100%;
}
.contact-us-submit-button:hover {
  transform: scale(1.03);
}
.el-form-item {
  width: 100% !important;
}
.el-form {
  max-width: 845px !important;
  width: 100% !important;
}
</style>
