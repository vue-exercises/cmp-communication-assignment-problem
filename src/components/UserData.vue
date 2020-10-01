<template>
  <form @submit.prevent="submitForm">
    <div class="cont">
      User
      <input type="text" v-model="enteredUsername" />
    </div>
    <br />
    <div class="cont">
      Age
      <input type="text" v-model="enteredAge" />
    </div>
    <br />
    <button>Show user</button>
  </form>
</template>

<script>
export default {
  emits: ["add-user"],
  data() {
    return {
      enteredUsername: "",
      enteredAge: "",
    }
  },
  methods: {
    submitForm() {
      this.$emit("add-user", this.enteredUsername, this.enteredAge)
    },
  },
}
</script>
