<template>
  <div id="app">
    <img src="./assets/logo.png" class="img-left" alt />
    <div id="registration-container">
      <main id="center-box">
        <Registration />
      </main>
      <img src="./assets/logo.png" class="img-right" alt />
    </div>
  </div>
</template>

<script>
import Registration from "./components/Registration";

export default {
  name: "App",
  components: {
    Registration
  }
};
</script>

<style>
body {
  background-color: #ffffff;
  width: 100%;
  height: 100%;
  margin: 0;
  padding: 0;
}

body,
html,
#app {
  height: 100vh;
  overflow: hidden;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}

#registration-container {
  width: 100%;
  height: 100%;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-grow: 1;
}

#center-box {
  width: 60%;
  margin: auto auto;
  position: absolute;
}

img {
  position: absolute;
}

.img-right {
  top: 30%;
  left: 70%;
}

.img-left {
  z-index: 2;
  bottom: 30%;
  right: 70%;
}

@media (min-width: 1600px) {
  .img-right {
    left: 75%;
  }

  .img-left {
    right: 75%;
  }
}
</style>