<template>
    <div>
        <h3>Crid</h3>
        <v-card class="mt-5 mb-8">
            <v-card-text>
                <v-container pa-0>
                    <v-row no-gutters>
                        <v-col cols="12" sm="6" offset-sm="3">
                            <v-card
                                class="pa-2"
                                outline
                                tile
                                >
                                Column
                            </v-card>
                        </v-col>
                    </v-row>
                    <v-row no-gutters>
                        <v-col cols="4">
                            <v-card
                                class="pa-2"
                                outline
                                tile
                                >
                                Column
                            </v-card>
                        </v-col>
                        <v-col cols="4">
                            <v-card
                                class="pa-2"
                                outline
                                tile
                                >
                                Column
                            </v-card>
                        </v-col>
                        <v-col cols="4">
                            <v-card
                                class="pa-2"
                                outline
                                tile
                                >
                                Column
                            </v-card>
                        </v-col>
                    </v-row>
                </v-container>
            </v-card-text>
        </v-card>
    </div>
</template>

<script>
    export default {
        layout: 'theatre'
    }
</script>

<style scoped>
    .container {
        border: solid 1px green;
    }
    .row {
        border: solid 1px red;
    }
    .col {
        border: solid 1px blue;
    }
</style>