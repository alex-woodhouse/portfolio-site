<template>
  <div>
    <div class="project-container">
      <div v-if="project.logoURL" class="pr-2">
        <v-img contain class="logo-container my-1 mr-3" max-height="70" max-width="70" :src="project.logoURL" alt="Logo" />
      </div>
      <div>
        <div class="project-name"> {{ project.name }}</div>
        <div class="project-spacer"></div>
        <div style="display: flex;">
          <a v-if="project.websiteURL" :href="project.websiteURL" target="_blank" style="display: flex;">
            <v-icon size="20" color="white">mdi-web</v-icon>
            <div class="px-3 white--text">Website</div>
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'ProjectHeader',

  props: {
    project: {
      type: Object,
      required: true,
    },
  },

}
</script>

<style lang="scss" scoped>
.project-container {
  display: flex;
  align-items: self-start;
  width: available;
}

.logo-container {
  border-radius: 12px;
  overflow: hidden;
  background-color: white;
  width: 70px;
  height: 70px;
}

.project-name {
  font-size: 22px;
  padding-top: 8px;
  font-weight: 500;
  color: white;
  //Wrap text onto new line if exceeds max width
  word-wrap: break-word;
  word-break: break-all;
  hyphens: auto;
}

.project-spacer {
  padding-bottom: 5px;
}

.separating-dot {
  color: white;
  padding: 0 15px 0 10px;
}

a {
  color: #c6c6c6;
  text-decoration: none; /* no underline */
}
</style>
