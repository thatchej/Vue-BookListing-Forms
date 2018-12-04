<template>
  <form v-on:submit.prevent="bookSubmit(bookData)" class="" action="#" method="post">
    <input v-model="bookData.bookTitle" type="text" name="title" value="" placeholder="Book Title">
    <input v-model="bookData.bookAuthor" type="text" name="author" value="" placeholder="Book Author">
    <div>
      <label for="finishedReading">Finished Reading</label>
      <input v-model="bookData.finishedReading" type="checkbox" id="finishedReading" name="finished" value="" placeholder="Finished Reading">
    </div>
    <label for="borrowed">Borrowed</label>
    <input v-model="bookData.ownership" type="radio" id="borrowed" name="finished" value="borrowed" placeholder="Finished Reading">
    <label for="bought">Bought</label>
    <input v-model="bookData.ownership" type="radio" id="bought" name="finished" value="bought" placeholder="Finished Reading">
    <button type="submit" name="button">Add Book</button>
  </form>
</template>

<script>
export default {
  name: "BookForm",
  props: ["books"],
  data() {
    return {
      bookData: {
        bookTitle: "",
        bookAuthor: "",
        finishedReading: false,
        ownership: []
      }
    };
  },
  methods: {
    bookSubmit(bookData) {
      this.$emit("addBook", bookData);
    }
  }
};
</script>

<style>
</style>
