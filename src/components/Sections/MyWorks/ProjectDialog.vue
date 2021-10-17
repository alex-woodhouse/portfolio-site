<template>
  <v-dialog v-model="dialog" width="820px">
    <template #activator="{ on, attrs }">
      <v-card
          light
          class="ma-2 elevation-0 rounded-lg"
          width="350px"
          v-bind="attrs"
          v-on="on"
          outlined
      >
        <v-img
            class="align-end white"
            height="200px"
            contain
            :src="bannerURL"
        />
        <div>
          <div id="project-title">
            {{ project.name }}
          </div>
          <div id="project-subtitle">
            {{ project.subtitle }}
          </div>
          <v-chip-group
              active-class="primary--text"
              column
              class="pl-3 pb-2"
          >
            <v-chip
                v-for="tag in project.tags"
                :key="tag"
            >
              {{ tag }}
            </v-chip>
          </v-chip-group>
        </div>
      </v-card>
    </template>

    <div class="rounded-lg pa-1 primary">
      <div id="close-btn" @click="closeDialog">
        <v-icon id="close-btn-icon" color="white">mdi-close</v-icon>
      </div>
      <iframe
          v-if="dialog && project.iframeURL"
          id="project-video"
          type="text/html"
          width="97.5%"
          height="400"
          :src="project.iframeURL"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
      />
      <v-img
          v-else
          class="white--text align-end rounded-lg ma-3 white"
          height="400px"
          contain
          :src="bannerURL"
      />
      <div id="project-header">
        <ProjectHeader class="ml-2" :project="project" />
        <div class="white--text mt-3 ml-2" v-html="project.subtitle" />
      </div>
    </div>
  </v-dialog>
</template>

<script>
import ProjectHeader from "@/components/Sections/MyWorks/ProjectHeader";

let videoPlayer = document.getElementById('project-video');

export default {
  name: 'ProjectDialog',

  components: { ProjectHeader },

  props: {
    project: {
      type: Object,
      required: true,
    },
  },

  data() {
    return {
      dialog: false,
    }
  },

  computed: {
    bannerURL() {
      return this.project?.bannerURL
    },
  },

  methods: {
    closeDialog() {
      this.dialog = false;
      var iframe = videoPlayer.querySelector( 'iframe');
      var video = videoPlayer.querySelector( 'video' );
      if ( iframe ) {
        var iframeSrc = iframe.src;
        iframe.src = iframeSrc;
      }
      if ( video ) {
        video.pause();
      }
    }
  }
}
</script>

<style lang="scss">
#close-btn {
  background-color: black;
  border-radius: 30px;
  width: 30px;
  height: 30px;
  z-index: 1;
  position: absolute;
  margin-left: -15px;
  margin-top: -15px;
  cursor: pointer;
}

#close-btn-icon {
  padding-top: 3px;
  padding-left: 3px;
}

#project-video {
  margin: 10px 10px 0 10px;
  border-radius: 12px;
  overflow: hidden;
}

#project-header {
  padding: 13px;
  margin: 10px 8px 12px 10px;
  background-color: var(--v-secondary-base);
  border-radius: 12px;
}

#project-title {
  font-weight: bold;
  font-size: 20px;
  margin: 15px 0 0 20px;
}

#project-subtitle {
  margin: 5px 30px 10px 20px;
  font-size: 14px;
  display: block;
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
}
</style>
