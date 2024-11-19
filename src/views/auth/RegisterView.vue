<script setup>
import { ref } from 'vue'

const theme = ref('light')

function onClick() {
  theme.value = theme.value === 'light' ? 'dark' : 'light'
}
</script>

<template>
  <v-responsive class="border rounded">
    <v-app :theme="theme">
      <v-app-bar class="px-3" color="light-blue-lighten-2">
        <v-spacer></v-spacer>

        <v-btn
          :prepend-icon="
            theme === 'light' ? 'mdi-weather-sunny' : 'mdi-weather-night'
          "
          text="Toggle Theme"
          slim
          @click="onClick"
        ></v-btn>
      </v-app-bar>

      <v-main>
        <v-container>
          <!-- <h1>Main Content</h1> -->
        </v-container>
        <!-- ! 1 row -->
        <v-row class="d-flex justify-center">
          <!-- ! 1 col -->
          <v-col cols="12" md="6" class="mx-auto">
            <!-- !! v card -->
            <v-card class="glass-card border-thin" text="">
              <v-form class="px-3 pb-3" fast-fail @submit.prevent>
                <!-- !! first name -->
                <v-text-field
                  v-model="userName"
                  :rules="userNameRules"
                  label="First Name"
                  variant="outlined"
                ></v-text-field>

                <!-- !! last name -->
                <v-text-field
                  v-model="userName"
                  :rules="userNameRules"
                  label="Last Name"
                  variant="outlined"
                ></v-text-field>

                <!-- !! Email -->
                <v-text-field
                  v-model="userName"
                  :rules="userNameRules"
                  label="Email"
                  variant="outlined"
                ></v-text-field>

                <!-- !! Password -->
                <v-text-field
                  v-model="password"
                  :rules="passwordRules"
                  label="Password"
                  variant="outlined"
                  type="password"
                ></v-text-field>

                <!-- !! Confirm Password -->
                <v-text-field
                  v-model="password"
                  :rules="passwordRules"
                  label="Confirm Password"
                  variant="outlined"
                  type="password"
                ></v-text-field>

                <v-btn
                  block
                  variant="outlined"
                  rounded="xl"
                  size="x-large"
                  class="mt-2"
                  type="submit"
                  >Register</v-btn
                >
                <p class="text-center mt-3">Forgot Password?</p>
                <br />
                <p class="text-center">
                  Already have an account?
                  <RouterLink to="/" class="text-primary">Login</RouterLink>
                </p>
                <br /> </v-form
            ></v-card>
          </v-col>
        </v-row>
      </v-main>

      <!-- ! footer -->
      <!-- <v-footer border app class="bg-grey-lighten-1" color="primary">
        <v-row justify="center" no-gutters>
          <v-btn
            v-for="link in links"
            :key="link"
            class="mx-2"
            color="white"
            rounded="xl"
            variant="text"
          >
            {{ link }}
          </v-btn>
          <v-col class="text-center" cols="12">
            {{ new Date().getFullYear() }} — <strong>App name</strong>
          </v-col>
        </v-row>
      </v-footer> -->
    </v-app>
  </v-responsive>
</template>
