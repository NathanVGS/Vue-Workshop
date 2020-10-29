<template>
  <div id="teacher-form">
    <form @submit.prevent="handleSubmit">
      <label>teacher name</label>
      <input v-model="teacher.name" type="text" />
      <label>teacher Email</label>
      <input v-model="teacher.email" type="text" />

      <button>Add teacher</button>
     <!-- <input type="submit" value="Add teacher"/>-->
    </form>
  </div>
</template>

<script>
export default {
  name: 'teacher-form',
  data() {
    return {
      teacher: {
        name: '',
        email: '',
      },
    }
  },
  methods: {
    handleSubmit() {
      console.log('testing handleSubmit')
      this.$emit('add:teacher', this.teacher)
    },
  },
}
</script>

<style scoped>
form {
  margin-bottom: 2rem;
}
</style>