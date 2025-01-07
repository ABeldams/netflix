<script>
import axios from "axios";

export default {
  name: "moviesCard",
  data() {
    return {
      movies: [],
      isLoading: false,
      currentPage: 1,
      moviesPerPage: 6, 
    };
  },
  computed: {
    paginatedMovies() {
      const startIndex = (this.currentPage - 1) * this.moviesPerPage;
      return this.movies.slice(startIndex, startIndex + this.moviesPerPage);
    },
    totalPages() {
      return Math.ceil(this.movies.length / this.moviesPerPage);
    },
  },
  methods: {
    async fetchMovies() {
      this.isLoading = true;
      try {
        const response = await axios.get("https://www.apirequest.in/movie/api");
        this.movies = response.data;
      } catch (error) {
        console.error("Error fetching movies:", error);
      } finally {
        this.isLoading = false;
      }
    },
    nextPage() {
      if (this.currentPage < this.totalPages) {
        this.currentPage++;
      }
    },
    previousPage() {
      if (this.currentPage > 1) {
        this.currentPage--;
      }
    },
  },
  mounted() {
    this.fetchMovies();
  },
};
</script>

<template>
<section class="py-16 bg-black">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <!-- Section Header -->
    <div class="flex items-left justify-between mb-6">
      <h2 class="text-2xl font-bold text-white">Trending Now</h2>
      <div class="flex space-x-4">
        <select class="bg-gray-800 text-white p-2 rounded focus:outline-none focus:ring-2 focus:ring-red-600">
          <option>Nigeria</option>
          <option>USA</option>
          <option>India</option>
        </select>
        <select class="bg-gray-800 text-white p-2 rounded focus:outline-none focus:ring-2 focus:ring-red-600">
          <option>Movies</option>
          <option>TV Shows</option>
        </select>
      </div>
    </div>

    <!-- Movie Cards -->
    <div class="grid grid-cols-3 gap-4">
      <div
        class="relative w-full h-[300px] shrink-0 mt-12"
        v-for="movie in paginatedMovies"
        :key="movie.id"
      >
        <img
          :src="movie.Images[1]"
          :alt="movie.title"
          class="w-full h-48 object-cover rounded-lg"
        />
        <div class="p-4">
          <h3 class="text-lg font-semibold text-white">{{ movie.title }}</h3>
          <p class="text-white">{{ movie.plot }}</p>
        </div>
      </div>
    </div>

    
    <div class="flex justify-between items-center mt-12">
      <button
        class="bg-red-600 text-white px-4 py-2 rounded focus:outline-none focus:ring-2 focus:ring-red-600"
        @click="previousPage"
        :disabled="currentPage === 1"
      >
        Previous
      </button>
      <span class="text-white">Page {{ currentPage }} of {{ totalPages }}</span>
      <button
        class="bg-red-600 text-white px-4 py-2 rounded focus:outline-none focus:ring-2 focus:ring-red-600"
        @click="nextPage"
        :disabled="currentPage === totalPages"
      >
        Next
      </button>
    </div>
  </div>
</section>
</template>

<style scoped>
/* Optional Styling */
button:disabled {
  opacity: 0.5;
  cursor: not-allowed;
}
</style>
