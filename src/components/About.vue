<template>
  <v-container>
    <v-card flat>
      <v-card-title>About me</v-card-title>
      <v-card-text>
        <p>
          Lately I've been updating my programming knowledge to better suit
          today's technologies.
        </p>
        <p>
          I'm doing this because I've always found IT and programming very
          interesting, and of course to find a meaningful career in software
          development.
        </p>
        <p>
          As a person I am very reliable, positive, exemplary and always seeking
          to be as knowledgeable as possible.<br />
          As a colleague you'll find me very helpful and friendly.
        </p>
        <p>
          I've gathered a fair amount of experience over the years, mostly in
          customer service. <br />
          This has given me quite good people skills although I'm probably more
          of an introvert than an extrovert.
        </p>
      </v-card-text>
    </v-card>
    <v-card flat>
      <v-card-title>Skills</v-card-title>
      <div class="text-center">
        <v-chip v-for="skill in skills" :key="skill">{{ skill }}</v-chip>
      </div>
    </v-card>
  </v-container>
</template>

<script>
export default {
  name: 'About',
  data() {
    return {
      skills: [],
    };
  },
  created() {
    fetch('skills.json')
      .then((response) => response.json())
      .then((data) => (this.skills = data.skills))
      .catch((error) => console.log(error));
  },
};
</script>
