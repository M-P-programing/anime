<template>
  <div class="hello">
    <h1>Hello</h1>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Magnam quos
      voluptas soluta cum laudantium velit unde laborum esse quis, aspernatur
      deleniti recusandae, aliquid, reprehenderit dolorum ut culpa! Velit itaque
      quasi aliquam quod. Sint expedita quisquam facere corporis eaque ducimus,
      id delectus cum fugiat perferendis, nisi possimus? Animi optio sunt eum,
      nostrum accusantium ratione id eaque? Est quaerat ut expedita, nemo aut a
      facere dolor, explicabo minima sit eveniet, soluta omnis laboriosam
      corporis itaque porro perferendis id officiis atque dolorum enim? Nisi,
      error. Optio, illum quas nisi debitis eligendi suscipit expedita,
      necessitatibus aut laudantium ut excepturi odio reiciendis. Eveniet,
      fugiat repellendus?
    </p>
    <p>{{ data }}</p>
  </div>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      data: [],
    };
  },
  mounted() {
    const headers = { Accept: "application/json" };
    fetch(process.env.VUE_APP_API_URL, { headers })
      .then((res) => res.json())
      .then((data) => (this.data = data))
      .catch((err) => console.log(err.message));
    console.log(process.env.VUE_APP_API_URL);
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: $black;
}
</style>
