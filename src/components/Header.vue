<template>
    <div>
      <v-navigation-drawer temporary>
    </v-navigation-drawer>
    <v-toolbar dark class="primary">
      <v-toolbar-side-icon
        class="hidden-sm-and-up "></v-toolbar-side-icon>
      <v-toolbar-title>Quizzer</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-xs-only">
        <v-btn flat>
          <v-icon left dark>supervisor_account</v-icon>
          Login
        </v-btn>
        <v-btn flat>
            Counter: 1/4
        </v-btn>
      </v-toolbar-items>
    </v-toolbar> 
    </div>
</template>
