<template>
     <v-app>
        <v-toolbar app class="primary">
        <v-toolbar-title v-text="'Учебный форум'"> </v-toolbar-title>
            <v-spacer></v-spacer>
            <v-toolbar-items>
                <v-btn >{{user}}</v-btn>
            </v-toolbar-items>
        </v-toolbar>
        <template v-if = "user === 'student'">
            <student_page />
        </template>
        <template v-else-if="user === 'teacher'">
            <teacher_page />
        </template>
        <template v-else>
            <authorization_form v-bind:checkUserFunc = "checkUserFunc"  v-bind:messageWithMistake = "messageWithMistake"/>
        </template>
     </v-app>

</template>





<script>
import authorization_form from './components/Authorization_form.vue';
import student_page from './components/Student_page.vue';
import teacher_page from './components/Teacher_page.vue';

export default {
  name: 'App',

  components: {
      authorization_form,
      student_page,
      teacher_page
  },

    data() {
        return {
            user: null,
            messageWithMistake: null
        }
    },

    methods: {
    checkUserFunc: function (login, password) {
       if (login === "student" && password ==="sdemo") {
           console.log( "Вы вошли как student");
           this.user = "student";
       }
       else if (login === "teacher" && password ==="tdemo") {
           console.log( "Вы вошли как teacher");
           this.user = "teacher";
       }
       else {
           this.messageWithMistake = "Вы ввели неправильные данные";
       }
    }
    }
};
</script>
