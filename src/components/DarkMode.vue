<template>
  <div class="container" :class="{ 'dark-mode': darkMode }">
    <img alt="Vue logo" src="../assets/logo.png" />
    <h1>Vue JS</h1>

    <h2>{{ text }}</h2>

    <div class="img" :class="{ 'img-dark': darkMode }">
      <img :src="img" alt="" />
    </div>

    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Illum, quisquam
      ad placeat beatae nostrum numquam. Minima voluptate sunt ab? Fugiat neque
      deleniti iure porro quidem nihil, exercitationem tenetur quod accusamus.
    </p>

    <button @click="changeModes((darkMode = !darkMode))">Change</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      darkMode: false,
      text: "Light Mode",
      img: "https://www.flaticon.com/svg/static/icons/svg/979/979585.svg",
    };
  },

  methods: {
    changeModes(boolean) {
      this.darkMode = boolean;
      this.text = !this.darkMode ? "Light Mode" : "Dark Mode";
      this.img = !this.darkMode
        ? "https://www.flaticon.com/svg/static/icons/svg/979/979585.svg"
        : "https://www.flaticon.com/svg/static/icons/svg/3226/3226413.svg";
    },
  },
};
</script>

<style scoped>
.container {
  width: 100vw;
  height: 100vh;
  background: #fff;

  transition: all 0.7s;
}

.container button {
  padding: 10px 20px;
  margin: 10px;

  border: none;
  border-radius: 5px;

  font-weight: 700;
  color: #383838;
}

.container img {
  width: 120px;
}

.container h2,
.container p {
  padding: 10px 2px;
}

.container p {
  width: 500px;
  margin: auto;
}

.img {
  width: 100px;
  height: 100px;
  margin: 10px auto;
  padding: 30px;
  background: #f2f2f2;
  border-radius: 100px;
}

.img img {
  margin: auto;

  position: relative;
  left: -10px;
  top: -10px;
}

.dark-mode {
  background: #0e0e0e;
}

.dark-mode button {
  background: #383838;
  color: #f2f2f2;
}

.img-dark {
  background: #383838;
}

.dark-mode h1 {
  color: #82d3af;
}

.dark-mode p,
.dark-mode h2 {
  color: #fff;
}
</style>