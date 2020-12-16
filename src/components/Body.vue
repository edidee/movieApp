<template>
  <div class="body-div">
    <b-form-input v-model="search" @keyup="submit" placeholder="Enter a movie title" class="search-bar"  ref="input"></b-form-input>
        
    <div class="d-flex justify-content-between row">
      <div class="col-lg-4">
        <img :src="imgUrl + info.poster_path" alt="" class="img-fluid" />
      </div>
      <div class="col-lg-5">
        <h2>{{ info.title }}</h2>
        <p>{{ info.genres[0].name }}</p>
        <p>
          {{info.overview}}
        </p>
        <p><span>Released Date:</span>{{ info.release_date }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Body",
  props: ["info"],

  unmounted() {
    console.log(this.info);
  },

  data() {
    return {
      imgUrl: "https://image.tmdb.org/t/p/w500",
      dataObject: {
          searchValue: null
      },
      search: '',
      input: ''
    };
  },
  methods: {
   submit() {
            this.$emit('submit', this.search)
        }
  },
};
</script>

<style scoped>
  .search-bar{
        width: 20%;
        float: right;
        margin-top: 2%;
        margin-right: 3%;
        border: 1px solid #93020B;
    }

.body-div {
  clear: both;
  height: auto;
}
</style>