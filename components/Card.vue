<template>
    <v-container>
                <!-- <v-card
                    target="_blank"
                    :href="url"
                    class="mx-auto"
                    max-width="5450"
                >
                    <v-img
                        :src="image"
                        width="400"
                        height="250"
                    ></v-img>

                    <v-card-title
                        v-text="title">
                    </v-card-title>
                </v-card> -->
                 <iframe width="420" height="315"
                :src="url" 
                allowfullscreen></iframe>
    </v-container>
</template>

<script>
export default {
    props: ['title', 'image', 'url']
}
</script>

<style scoped>
</style>