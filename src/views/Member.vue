

<template>
  <div id="register">
    <h1>歡迎！</h1>
    <Form/>
    <!--
    <qr-code text="xxx"></qr-code>
    -->
  </div>
</template>
<script>
import Form from '../components/Form.vue'

export default {
  name: 'register',
  components: {
    Form
  }
}
</script>