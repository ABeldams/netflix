<script>
export default{
    name:'welcome'

};
</script>
<template>

<div class="relative m h-screen bg-cover bg-center">
    <!-- Overlay -->
    <div class="absolute inset-0 bg-black bg-opacity-50"></div>

    <!-- Content -->
    <div class="relative z-10 flex flex-col items-center justify-center h-full text-center px-4">
      <h1 class="text-4xl text-white md:text-6xl font-bold mb-4">Unlimited movies, TV <br> shows, and more</h1>
      <p class="text-lg md:text-xl mb-6 text-white">Starts at ₦2,200. Cancel anytime.</p>
      <p class="text-sm md:text-base mb-4 text-white">Ready to watch? Enter your email to create or restart your membership.</p>
      
      <!-- Input and Button -->
      <div class="flex flex-col md:flex-row items-center w-full md:w-1/2">
        <input 
          type="email" 
          placeholder="Email address" 
          class="w-full p-3 text-gray-200 rounded md:rounded-l-md outline-none focus:ring-2 focus:ring-red-600 bg-black border border-white"
        />
        <button 
          class="mt-2 md:mt-0 md:ml-2 bg-red-600 text-white font-bold w-[300px] h-[50px] rounded md:rounded-r-md hover:bg-red-700"
        >
          Get Started &RightAngleBracket;
        </button>
      </div>
    </div>

    <!-- Sign In Button -->
    <div class="absolute top-20 right-20">
      <button class="bg-red-600 text-white font-semibold px-4 py-2 rounded hover:bg-red-700">
        Sign In
      </button>
    </div>
	
	<!-- Sign In Button -->
    <div class="absolute top-4  left-20">
      <img src="../assets/netflix_logo.png" class="w-[150px] h-[150px]"/>
    </div>
	
  </div>
  

</template>
<style scoped>

.m{

background-image: url('../assets/net.JPG');

}
</style>
