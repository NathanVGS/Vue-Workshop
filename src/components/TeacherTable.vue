<template>
  <div id="teacher-table">
    <table>
      <thead>
      <tr>
        <th>Teacher name</th>
        <th>Teacher email</th>
      </tr>
      </thead>
      <tbody>
      <tr v-for="teacher in teachers" :key="teacher.id">
        <td>{{ teacher.name }}</td>
        <td>{{ teacher.email }}</td>
      </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: 'teacher-table',
  props: {
    teachers: Array,
  },
}
</script>

<style scoped></style>