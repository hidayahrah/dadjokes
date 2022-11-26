<template>
    <form @submit.prevent="onSubmit">
        <input type="text" v-model="text" placeholder="Search Jokes..." class="input-search">
        <input type="submit" value="Search Jokes" class="search">
    </form>
</template>

<script>
export default {
    name: 'SearchJokes',
    data() {
        return {
            text: ""
        };
    },
    methods: {
        onSubmit() {
            this.$emit('search-text', this.text);
            this.text = "";
        }
    }
}
</script>
<style>
.search {
  display: inline-block;
  background: hsl(180deg 97% 22%);
  color: #fff;
  padding: 0.3rem 1rem;
  margin-right: 0.5rem;
  border-color: hsl(180deg 97% 22%);
}
.input-search {
  display: inline-block;
  background: #fff;
  color: #333;
  padding: 0.3rem 1rem;
  margin-right: 0.5rem;
}
</style>