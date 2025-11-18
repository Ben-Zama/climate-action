<template>
  <section id="success" ref="mainSection">
    <div class="heading">
      <h2>Climate Change Success Stories</h2>
      <p>Real people. Real action. Real impact.</p>
    </div>

    <Swiper
      class="stories"
      :modules="[Autoplay, Pagination]"
      :loop="true"
      :autoplay="{ delay: 5000 }"
      :pagination="{ clickable: true }"
      :slides-per-view="1"
      :space-between="15"
      :breakpoints="{
        600: {
          slidesPerView: 2,
        },
        1024: {
          slidesPerView: 3,
        },
      }"
    >
      <SwiperSlide v-for="(story, index) in stories" :key="index" class="card">
        <img :src="story.image" :alt="story.title" />
        <div class="content">
          <h3>{{ story.title }}</h3>
          <p>{{ story.description }}</p>
          <span>{{ story.tag }}</span>
        </div>
      </SwiperSlide>
    </Swiper>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";
import { Swiper, SwiperSlide } from "swiper/vue";
import { Autoplay, Pagination } from "swiper/modules";

import gsap from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);

const mainSection = ref(null);
let ctx; 

const stories = [
  {
    title: "Kenya’s Solar Village",
    description:
      "A remote village once dependent on diesel now runs fully on solar power. Women-led cooperatives manage the grids — cutting emissions by 80% and boosting local businesses.",
    tag: "#RenewableRevolution",
    image: "/success/solar-village.jpg",
  },
  {
    title: "Philippines Reforestation Drive",
    description:
      "Over 2 million trees planted in less than a year — reviving mangroves, restoring biodiversity, and protecting entire coastal villages from floods.",
    tag: "#GreenRoots",
    image: "/success/reforestation.jpg",
  },
  {
    title: "Germany’s Energy Transition",
    description:
      "Through bold policy and public support, Germany now generates over 50% of its electricity from renewable sources — a model for sustainable growth.",
    tag: "#Energiewende",
    image: "/success/germany-energy.jpg",
  },
  {
    title: "Costa Rica’s Carbon Neutral Push",
    description:
      "Costa Rica runs on nearly 100% renewable electricity and aims to become the first carbon-neutral country — proving green living is achievable.",
    tag: "#PureEnergy",
    image: "/success/costa-rica.webp",
  },
  {
    title: "Netherlands Flood Defense Innovation",
    description:
      "Using smart water management, floating homes, and restored wetlands, the Netherlands has turned flood risk into climate resilience.",
    tag: "#SmartAdaptation",
    image: "/success/netherlands.jpg",
  },
  {
    title: "India’s Solar-Powered Schools",
    description:
      "Thousands of rural schools in India now run on solar energy — lowering costs and teaching kids the power of sustainability.",
    tag: "#BrightFutures",
    image: "/success/india-schools.jpg",
  },
  {
    title: "Morocco’s Desert Solar Farm",
    description:
      "One of the world’s largest concentrated solar plants in Ouarzazate powers over a million homes and creates thousands of green jobs.",
    tag: "#DesertSun",
    image: "/success/morocco-solar.jpg",
  },
  {
    title: "Anna’s Daily Ride",
    description:
      "Instead of driving, Anna bikes 15 km to work every day. She’s reduced over 1 ton of CO₂ emissions yearly — and her company followed her lead by installing bike stations for all staff.",
    tag: "#PedalForPlanet",
    image: "/success/anna-bike.jpg",
  },
  {
    title: "Leo’s Urban Garden",
    description:
    "Leo transformed his small balcony into a thriving micro garden. It now provides fresh food for his family and has inspired over 200 locals to start home gardens across the city.",
    tag: "#GrowLocal",
    image: "/success/leo-garden.jpg",
  },
];

onMounted(() => {
  ctx = gsap.context(() => {
    
    const initialSlides = gsap.utils.toArray(".swiper-slide-active, .swiper-slide-next"); 

    const tl = gsap.timeline({
      scrollTrigger: {
        trigger: mainSection.value,
        start: "top 75%",
        toggleActions: "play none none reverse",
      },
    });
    tl.from(".heading", {
      y: 30,
      opacity: 0,
      duration: 0.6,
      ease: "power2.out",
    })
    .from(".swiper-slide", {
        y: 50,
        opacity: 0,
        duration: 0.8,
        stagger: 0.15,
        ease: "back.out(1.2)",
    }, "-=0.3");
    
  }, mainSection.value); 
});

onUnmounted(() => {
  ctx.revert();
});
</script>

<style lang="scss">
#success {
  margin: 25px 0;
  padding: 25px;
  background: var(--accent);

  .heading {
    text-align: center;
    h2 {
      font-size: 25px;
      font-weight: 900;
    }
  }

  .stories {
    margin-top: 25px;

    .swiper-wrapper {
      display: flex;
      align-items: stretch;
    }

    .swiper-pagination {
      margin-top: 25px;
      display: flex;
      justify-content: center;
      gap: 15px;
      .swiper-pagination-bullet {
        display: block;
        width: 10px;
        height: 10px;
        background: var(--primary);
        border-radius: 50%;
        opacity: 0.5;
        cursor: pointer;
      }
      .swiper-pagination-bullet-active {
        background: var(--primary);
        opacity: 1;
      }
    }

    .card {
      height: auto;
      background: #f7f7f7;
      border: 1px solid #0f570f25;
      border-radius: 16px;
      overflow: hidden;
      display: flex;
      flex-direction: column; 
      img {
        width: 100%;
        height: 250px;
        object-fit: cover;
      }
      .content {
        flex: 1;
        padding: 25px;
        display: flex;
        flex-direction: column;
        gap: 15px;
        text-align: left;
        h3 {
          font-weight: bold;
          font-size: 20px;
          color: var(--primary);
        }
        span {
          font-family: var(--alternate-font);
          font-weight: bold;
          color: var(--primary);
        }
      }
    }
  }
}

@media (min-width: 600px) and (max-width: 1023px) {
  #success {
    margin: 50px 0;
    padding: 50px 25px;
  }
}

@media (min-width: 1024px) {
  #success {
    margin: 50px 0;
    padding: 50px 100px;
    .heading {
      h2 {
        font-size: 35px;
      }
    }
  }
}
</style>