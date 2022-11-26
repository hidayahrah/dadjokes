<template>
  <footer class="footer">
    <h5 class="title">© 2022 All rights reserved.</h5>
    <ul>
      <a href="https://hidayahrah.github.io/portfolio"><h5>GitHub</h5></a>
      <a href="https://www.linkedin.com/in/hidayahrah/"><h5>LinkedIn</h5></a>
    </ul>
  </footer>
</template>

<script>
export default {
  name: "AppFooter"
};
</script>

<style>
.footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 5rem;
  border-top: 1px dotted #ccc;
}
.footer .title {
  color: #526488;
}
.footer ul {
  margin: revert;
  display: flex;
}
.footer a {
  display: inline-block;
  color: black;
  padding: 0.3rem 1rem;
  margin: auto;
}
</style>
