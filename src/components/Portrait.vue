<template>
  <v-sheet rounded="lg" min-height="268" min-width="150">
    <v-img
      class="mx-auto rounded-lg"
      src="../assets/Tapio-ekman.jpg"
      max-width="150"
      min-width="150"
    />
    <v-list-item>
      <v-list-item-content class="text-center grey--text text--darken-2">
        <v-list-item-title>
          <v-hover v-slot="{ hover }">
            <a href="mailto:tapio.ekman@gmail.com"
              ><v-icon :color="hover ? 'blue' : 'grey darken-2'" class="px-1"
                >mdi-email</v-icon
              ></a
            >
          </v-hover>
          <v-hover v-slot="{ hover }">
            <a href="https://github.com/belnerd"
              ><v-icon :color="hover ? 'blue' : 'grey darken-2'" class="px-1"
                >mdi-github</v-icon
              ></a
            >
          </v-hover>
          <v-hover v-slot="{ hover }">
            <a href="https://www.linkedin.com/in/tapio-ekman/"
              ><v-icon :color="hover ? 'blue' : 'grey darken-2'" class="px-1"
                >mdi-linkedin</v-icon
              ></a
            >
          </v-hover>
        </v-list-item-title>
      </v-list-item-content>
    </v-list-item>
  </v-sheet>
</template>

<script>
export default {
  name: 'Portrait',
};
</script>
