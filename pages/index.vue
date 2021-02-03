<template>
  <v-container>
    <div class="display-4 ma-4 d-flex justify-center">
      All Videos
    </div>
      <v-row>
        <v-col 
          sm="12"
          md="6"
          lg="4"
          v-for="video in videos" :key="video.text">
          <Card 
                :title="video.snippet.title"
                :image="video.snippet.thumbnails.medium.url"
                :url="`http://www.youtube.com/embed/${video.id.videoId}`"
          />
        </v-col>
      </v-row>
        <v-footer
    dark
    padless
  >
    <v-card
      flat
      tile
      class="indigo lighten-1 white--text text-center"
    >
      <v-card-text>
        <v-btn
          v-for="icon in icons"
          :key="icon"
          class="mx-4 white--text"
          icon
        >
          <v-icon size="24px">
            {{ icon }}
          </v-icon>
        </v-btn>
      </v-card-text>

      <v-card-text class="white--text pt-0">
        Phasellus feugiat arcu sapien, et iaculis ipsum elementum sit amet. Mauris cursus commodo interdum. Praesent ut risus eget metus luctus accumsan id ultrices nunc. Sed at orci sed massa consectetur dignissim a sit amet dui. Duis commodo vitae velit et faucibus. Morbi vehicula lacinia malesuada. Nulla placerat augue vel ipsum ultrices, cursus iaculis dui sollicitudin. Vestibulum eu ipsum vel diam elementum tempor vel ut orci. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.
      </v-card-text>

      <v-divider></v-divider>

      <v-card-text class="white--text">
        {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
      </v-card-text>
    </v-card>
  </v-footer>
  </v-container>
</template>

<script>
import Card from '~/components/Card'

export default {
  async asyncData({$axios}) {
    let response = await $axios.get('https://youtube.googleapis.com/youtube/v3/search?part=snippet&maxResults=30&q=dota2&key=AIzaSyBDRlUPA0SC1HH142CXKvLegWBFKka5ZvQ')
    let videos = response.data.items

    return {
      videos
    } 
  },
      data: () => ({
      icons: [
        'mdi-facebook',
        'mdi-twitter',
        'mdi-linkedin',
        'mdi-instagram',
      ],
    }),
  components: {
    Card
  }
}
</script>
