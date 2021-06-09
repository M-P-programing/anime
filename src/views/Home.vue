<template>
  <div class="animes">
    <h1>Anime List</h1>
    <div class="anime-list">
      <div v-for="anime in animes.results" :key="anime" class="anime-card">
        <a href="#">
          <img v-bind:src="anime.image_url" alt="" />
        </a>
        <ul>
          <li>
            <p>{{ anime.title }}</p>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
 
  data() {
    return {
      animes: [],
    };
  },
  mounted() {
    const headers = { Accept: "application/json" };
    let page = this.$route.query.page
    fetch(
      process.env.VUE_APP_API_URL + "v3/search/anime?order_by=title&sort=asc&page=" + page,
      { headers }
    )
      .then((res) => res.json())
      .then((animes) => (this.animes = animes))
      .catch((err) => console.log(err.message));
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.animes {
  .anime-list {
    display: flex;
    flex-wrap: wrap;
    .anime-card {
      padding: 10px;
      max-width: 250px;
      a {
        img {
          width: 250px;
          height: 321px;
          vertical-align: middle;
          max-height: 321px;
          object-fit: cover;
        }
      }
      ul {
        margin-top: 10px;
        li {
          list-style-type: none;
        }
      }
      p {
        text-align: center;
      }
    }
  }
}
</style>
