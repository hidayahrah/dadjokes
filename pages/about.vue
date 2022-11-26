<template>
  <div>
    <h2>{{ title }}</h2>
    <p>
      <a href="https://icanhazdadjoke.com"><i>icanhazdadjoke.com</i></a>
      is the largest selection of dad jokes on the internet. Now supporting many
      different integrations to ensure you can access the dad jokes that you
      need wherever you are.
    </p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "About Dad Jokes",
    };
  },
  head() {
    return {
      title: "About Dad Jokes",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Best place for corny dad jokes",
        },
      ],
    };
  },
};
</script>