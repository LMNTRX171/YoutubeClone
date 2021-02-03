<template>
    <div>
        <v-row>
            <v-col 
            sm="12"
            md="6"
            lg="4"
            v-for="video in videoData" :key="video">
        <Card
            :title="video.snippet.title"
            :image="video.snippet.thumbnails.medium.url"
            :url="`http://www.youtube.com/embed/${video.id.videoId}`"
        />
            </v-col>
        </v-row>
    </div>
</template>

<script>
import Card from '~/components/Card'

    export default {
        async asyncData({$axios, params}) {
            let response = await $axios.get(`https://youtube.googleapis.com/youtube/v3/search?part=snippet&maxResults=30&q=${params.id}&key=AIzaSyBDRlUPA0SC1HH142CXKvLegWBFKka5ZvQ`)
            let videoData = response.data.items

            return {
                videoData
            }
        },
        components: {
            Card
        }
    }
</script>

<style lang="scss" scoped>

</style>