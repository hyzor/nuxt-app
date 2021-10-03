<template>
  <el-card class="card">
    <el-form
      ref="ruleForm"
      :model="contactForm"
      :rules="rules"
      label-width="0px"
    >
      <el-form-item prop="name">
        <el-input v-model="contactForm.name" class="input" placeholder="Name" />
      </el-form-item>
      <el-form-item prop="email">
        <el-input
          v-model="contactForm.email"
          class="input"
          placeholder="E-mail"
        />
      </el-form-item>
      <el-form-item prop="message">
        <el-input
          v-model="contactForm.message"
          type="textarea"
          :autosize="{ minRows: 2, maxRows: 6 }"
          placeholder="Message"
        />
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="submitForm('ruleForm')"
          >Send</el-button
        >
      </el-form-item>
    </el-form>
  </el-card>
</template>

<script>
export default {
  data() {
    return {
      contactForm: {
        name: '',
        email: '',
        message: '',
      },
      rules: {
        name: [
          { required: true, message: 'Please input name', trigger: 'blur' },
          { min: 3, message: 'Length should be at least 3', trigger: 'blur' },
        ],
        email: [
          { required: true, message: 'Please input e-mail', trigger: 'change' },
          {
            message: 'Please input a valid e-mail address',
            type: 'email',
            trigger: 'blur',
          },
        ],
        message: [
          {
            required: true,
            message: 'Please input message',
            trigger: 'change',
          },
          { min: 3, message: 'Length should be at least 3', trigger: 'blur' },
        ],
      },
    }
  },
  methods: {
    submitForm(formName) {
      this.$refs[formName].validate((valid) => {
        if (valid) {
          alert('Submit!')
        } else {
          return false
        }
      })
    },
  },
}
</script>

<style>
.card {
  max-width: 512px;
}
.input {
  max-width: 256px;
}
</style>
