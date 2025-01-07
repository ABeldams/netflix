<script>
export default{
name:'contact'

}
</script>
<template>
    <section class="bg-black">
<div class="py-10">
        <h2 class="text-1xl  mb-4 text-center">Ready to watch? Enter your email to create or restart your membership.</h2>
        
	 <!-- Input and Button -->
      <div class="m-auto flex flex-col md:flex-row items-center w-full md:w-1/2">
        <input 
          type="email" 
          placeholder="Email address" 
          class="w-full p-3 text-black rounded md:rounded-l-md outline-none focus:ring-2 focus:ring-red-600 bg-gray-900 border border-white"
        />
        <button 
          class="mt-2 md:mt-0 md:ml-2 bg-red-600 text-white font-bold w-[300px] h-[50px] rounded md:rounded-r-md hover:bg-red-700"
        >
          Get Started &RightAngleBracket;
        </button>
      </div>	
    </div>

</section>
</template>