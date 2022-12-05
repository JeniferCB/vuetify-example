<template>
  <div style="width: 300px;">
    <v-text-field
      label="Inser Email"
      :rules="emailRules"
      hide-details="auto"
      prepend-icon="mdi-at"
    ></v-text-field>
    <v-text-field
    label="Insert Password"
    :type="visible ? 'text' : 'password'"
    :rules="passwordRules"
    hide-details="auto"
    prepend-icon="mdi-lock"
    :append-icon="visible ? 'mdi-eye' : 'mdi-eye-off'"
    @click:append="visible = !visible"
    ></v-text-field>
  </div>
</template>

<script>
export default {
  data () {
    return {
      emailRules: [
        value => !!value || 'Email Required.',
        value => value.match(/^[a-zA-Z0-9]+(?:\.[a-zA-Z0-9]+)*@[a-zA-Z0-9]+(?:\.[a-zA-Z0-9]+)*$/) || 'Invalid Email Format'
      ],
      passwordRules: [value => value.length >= 5 || 'Password must be at least 5 characters long'],
      visible: false
    }
  }
}
</script>

<style scoped>
</style>
