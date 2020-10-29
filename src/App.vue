
<template>
  <div id="app" class="small-container">
    <h1>Becode Teachers</h1>

    <teacher-table :teachers="teachers" />
    <teacher-form @add:teacher="addTeacher"></teacher-form>
  </div>
</template>

<script>
import TeacherTable from '@/components/TeacherTable.vue'
import TeacherForm from '@/components/TeacherForm.vue'

export default {
  name: 'app',
  components: {
    TeacherTable,
    TeacherForm,
  },
  data() {
    return {
      teachers: [
        {
          id: 1,
          name: 'Koen Eelen,',
          email: 'koen@becode.org',
        },
        {
          id: 2,
          name: 'Tim Broos',
          email: 'tim@becode.org',
        },
        {
          id: 3,
          name: 'Sicco Smit',
          email: 'sicco@becode.org',
        },
      ],
    }
  },
  methods: {
    addTeacher(teacher) {
      const lastId = this.teachers.length > 0 ? this.teachers[this.teachers.length - 1].id : 0;
      const id = lastId + 1;
      const newTeacher = { ...teacher, id };

      this.teachers = [...this.teachers, newTeacher]
    }
  }
}
</script>

<style>
button {
  background: #009435;
  border: 1px solid #009435;
}

.small-container {
  max-width: 680px;
}
</style>

<!--
<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
-->
