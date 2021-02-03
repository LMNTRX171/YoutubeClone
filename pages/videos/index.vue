<template>
    <div>
      <form @submit.prevent="submit" class="display-4 ma-4 d-flex justify-center">
        <input
          placeholder="Search"
          v-model="search" 
          class="text-center citypiker"
          autofocus 
        />

      </form>
      <nuxt-child></nuxt-child>
    </div>
</template>

<script>
    export default {
        data: () => ({
            search: ''
        }),
        methods: {
            submit() {
                this.$router.push(`/videos/${this.search}`)
            }
        }
    }
</script>

<style scoped>
    .citypiker {
        width: 170px;
        padding: 5px 10px;
        box-sizing: border-box;
        box-shadow: 0 0 10px 0 #666;
        border: none;
        font-size: 18px;
        line-height: 16px;
        font-family: Arial;
        border-radius: 22px;
        outline:none;
    }
</style>