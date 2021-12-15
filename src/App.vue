<template>
  <v-app>
    <v-card-title class="text-center justify-center py-6 pb-0">
      <div class="font-weight-bold text-h2 grey--text text--darken-3">
        TAPIO EKMAN
      </div>
    </v-card-title>
    <v-app-bar class="flex-grow-0 text-center justify-center" color="white" flat>
      <v-tabs centered color="grey darken-1">
        <v-tab
          v-for="link in links"
          :key="link.id"
          @click="setMainComponent(link.id)"
        >
          {{ link.text }}
        </v-tab>
      </v-tabs>
    </v-app-bar>

    <v-main class="grey lighten-3">
      <v-container>
        <v-row>
          <v-col cols="12" sm="2">
            <Portrait />
          </v-col>

          <v-col cols="12" sm="7">
            <v-sheet min-height="70vh" rounded="lg">
              <div v-if="currentComponent === 0"><About /></div>
              <div v-if="currentComponent === 1"><Portfolio /></div>
              <div v-if="currentComponent === 2"><WorkAndEdu /></div>
            </v-sheet>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import Portrait from './components/Portrait.vue';
import About from './components/About.vue';
import Portfolio from './components/Portfolio.vue';
import WorkAndEdu from './components/WorkAndEdu.vue'

export default {
  name: 'App',

  components: { Portrait, About, Portfolio, WorkAndEdu },

  data: () => ({
    links: [
      { text: 'About me', id: 0 },
      { text: 'Portfolio', id: 1 },
      { text: 'Work & Education', id: 2 },
    ],
    currentComponent: 0,
  }),
  methods: {
    setMainComponent(id) {
      this.currentComponent = id;
    },
  },
};
</script>
