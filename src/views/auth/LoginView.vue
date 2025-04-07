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
      <!-- Dark Blue App Bar -->
      <v-app-bar class="px-3 bg-blue-darken-4" dark>
        <v-spacer></v-spacer>

        <v-btn
          :prepend-icon="theme === 'light' ? 'mdi-weather-sunny' : 'mdi-weather-night'"
          text="Toggle Theme"
          slim
          @click="onClick"
        ></v-btn>
      </v-app-bar>

      <v-main class="d-flex align-center justify-center" style="min-height: 100vh">
        <v-container>
          <v-row justify="center" align="center">
            <v-col cols="12" md="6">
              <v-card class="mx-auto">
                <template v-slot:title>
                  <div class="text-center">
                    <v-img class="mx-auto mb-2" src="logo final.jpg" width="25%"></v-img>
                    <span class="font-weight-black text-h6">Welcome to BooknHaven</span>
                  </div>
                </template>

                <v-card-text class="bg-surface-light pt-4">
                  <v-form fast-fail @submit.prevent>
                    <v-text-field v-model="email" :rules="email" label="Email"></v-text-field>

                    <v-text-field
                      v-model="password"
                      :rules="password"
                      label="Password"
                    ></v-text-field>

                    <v-btn class="mt-2" type="submit" block>Login</v-btn>
                  </v-form>
                </v-card-text>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </v-main>

      <!-- Dark Blue Footer -->
      <v-footer class="bg-blue-darken-4 text-white" app> 2025 - BooknHaven </v-footer>
    </v-app>
  </v-responsive>
</template>
