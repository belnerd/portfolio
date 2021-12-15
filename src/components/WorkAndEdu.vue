<template>
  <v-container class="pa-2" v-if="work">
    <v-tabs v-model="tab" centered color="grey darken-1">
      <v-tab>Work</v-tab>
      <v-tab>Education</v-tab>
      <v-tabs-items v-model="tab" class="pa-2">
        <v-tab-item>
          <v-card class="mb-2" tile v-for="item in work" :key="item.id">
            <div class="d-flex flex-no-wrap justify-space-between">
              <div>
                <v-card-title class="text-break">{{
                  item.header
                }}</v-card-title>
                <v-card-subtitle>{{ item.subtitle }}</v-card-subtitle>
                <v-card-text v-for="(desc, i) in item.description" :key="i">{{
                  desc
                }}</v-card-text>
              </div>
              <div>
                <a :href="item.url" :alt="item.url" target="_blank"
                  ><v-img
                    class="ma-2"
                    max-width="200"
                    max-height="150"
                    :src="item.img"
                  ></v-img
                ></a>
              </div>
            </div>
          </v-card>
        </v-tab-item>
        <v-tab-item>
          <v-card class="mb-2" tile v-for="item in education" :key="item.id">
            <div class="d-flex flex-no-wrap justify-space-between">
              <div>
                <v-card-title class="text-break">{{
                  item.header
                }}</v-card-title>
                <v-card-subtitle
                  >{{ item.title }} <br />
                  {{ item.subtitle }}</v-card-subtitle
                >
                <v-card-text v-for="(desc, i) in item.description" :key="i">{{
                  desc
                }}</v-card-text>
              </div>
            </div>
          </v-card>
        </v-tab-item>
      </v-tabs-items>
    </v-tabs>
  </v-container>
  <div v-else>Loading items...</div>
</template>

<script>
export default {
  name: 'WorkAndEdu',
  data() {
    return {
      work: [],
      education: [],
      tab: null,
    };
  },
  created() {
    fetch('cv_data.json')
      .then((response) => response.json())
      .then((data) => {
        this.work = data.work;
        this.education = data.education;
      })
      .catch((error) => console.log(error));
  },
};
</script>
