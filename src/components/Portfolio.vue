<template>
  <v-container class="pa-2" v-if="items">
    <v-card class="mb-1" tile v-for="item in items" :key="item.id">
      <div class="d-flex flex-no-wrap justify-space-between">
        <div>
          <v-card-title>{{ item.header }}</v-card-title>
          <v-card-text>{{ item.description }}</v-card-text>
          <v-card-actions>
            <v-btn :href="item.link" target="_blank">GIT/DOCS</v-btn>
            <v-btn v-if="item.demo" :href="item.demo" target="_blank"
              >DEMO</v-btn
            >
          </v-card-actions>
        </div>
        <div>
          <v-img max-width="200" max-height="150" :src="item.img"></v-img>
        </div>
      </div>
    </v-card>
  </v-container>
  <div v-else>Loading portfolio items...</div>
</template>

<script>
export default {
  name: 'Portfolio',
  data() {
    return {
      items: [],
    };
  },
  created() {
    fetch('data.json')
      .then((response) => response.json())
      .then((data) => (this.items = data.items))
      .catch((error) => console.log(error));
  },
};
</script>
