<template>
<div class="mx-[5%] md:mx-[9%]  md:flex justify-between md:mt-20">
  <h1 class="ptf text-4xl font-bold my-10 mt-20 md:w-[45%] md:mt-0">The Creative crew</h1>
  <div class="poppins md:w-[45%]">
    <h1 class="font-bold text-xl ">WHO WE ARE</h1>
    <p class="font-medium my-5 mb-14">We are team of creatively diverse. driven. innovative individuals working in various locations from the world.</p>
  </div>
</div>
<div class="grid grid-cols-2 md:grid-cols-3 gap-4  justify-center  ">
  <div v-for="(image, index) in images" :key="image.id" :class="getGridItemClass(index)" class=" mx-auto">
    <div class="flex">
      <img :src="image.url" :alt="image.alt" class="w-[75%]  md:w-[200px] md:h-[300px] object-cover" />
      <p class="p-2 w-0 whitespace-nowrap mt-[-10px] transform translate-x-[15px] lg:translate-x-[25px]  text-sm lg:text-lg h-0  rotate-90   ptf font-[400]">{{image.kerja}}</p>
    </div>
    <p class="font-bold poppins mt-2">{{image.nama}}</p>
  </div>
</div>

<div class="flex justify-center mt-20 py-5 w-full  mx-auto text-[#A9A9A9]">Created by <a href="https://www.instagram.com/fauzanyanuarputra/" class="underline mx-1">Fauzan</a> - devChallenges.io</div>
</template>

<script>
export default {
  data() {
    return {
      images: [{
          id: 1,
          kerja: "PRODUCT OWNER",
          nama: "Bill Mahoney",
          url: "photo1.png",
          alt: "photo 1"
        },
        {
          id: 2,
          kerja: "ART DIRECTOR ",
          nama: "Saba Cabrera",
          url: "photo2.png",
          alt: "photo 2"
        },
        {
          id: 3,
          kerja: "TECH LEAD",
          nama: "Shae Le",
          url: "photo3.png",
          alt: "photo 3"
        },
        {
          id: 4,
          kerja: "UX DESIGNER",
          nama: "Skylah Lu",
          url: "photo4.png",
          alt: "photo 4"
        },
        {
          id: 5,
          kerja: "DEVELOPER",
          nama: "Griff Richards",
          url: "photo5.png",
          alt: "photo 5"
        },
        {
          id: 6,
          kerja: "DEVELOPER",
          nama: "Stan John",
          url: "photo6.png",
          alt: "photo 6"
        },
      ],
      isMobile: false
    };
  },
  methods: {
    getGridItemClass(index) {
      if (this.isMobile) {
        if ((index + 1) % 2 === 0) {
          return "relative top-12";
        }
      } else {
        if ((index + 2) % 3 === 0) {
          return "relative top-12";
        }
      }
      return "";
    },
    handleResize() {
      this.isMobile = window.innerWidth < 768;
    }
  },
  mounted() {
    this.handleResize(); 
    window.addEventListener("resize", this.handleResize);
  },
  beforeUnmount() {
    window.removeEventListener("resize", this.handleResize);
  }
};
</script>

<style>
.grid {
  width: 100%;
}

.grid>* {
  padding: 1rem;
}

.poppins {
  font-family: 'Poppins', sans-serif;

}

.ptf {
  font-family: 'PT Serif', serif;

}
</style>
