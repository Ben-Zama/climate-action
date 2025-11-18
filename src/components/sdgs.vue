<template>
  <section id="sdgs" ref="mainSection">
    <div class="heading">
      <h2>Supporting the Global Goals</h2>
      <p>
        Climate action is Goal 13 of the United Nations Sustainable Development
        Goals — but every goal connects to a healthier planet and a fairer
        future.
      </p>
    </div>

    <div class="content">
      <a
        v-for="item in sdgs"
        :key="item"
        class="box sdg-box"
        :href="item.link"
        :style="item.color"
        target="_blank"
      >
        <div class="text">
          <p class="number">{{ item.number }}</p>
          <p class="name">{{ item.name }}</p>
        </div>
        <img :src="item.img" />
      </a>
      <a class="sdg global-goals-link" href="https://globalgoals.org/goals/" target="_blank">
        <img src="/sdg.png" alt="The 17 Global Goals logo" />
        <p>The Global Goals</p>
      </a>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";

// GSAP Imports
import gsap from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);

// --- REFS & DATA ---
const mainSection = ref(null);
let ctx; // GSAP Context variable for cleanup

const sdgs = [
  {
    number: 1,
    name: "No Poverty",
    img: "/goals/goal1.png",
    color: "background-color: #e5243c;",
    link: "https://globalgoals.org/goals/1-no-poverty/",
  },
  {
    number: 2,
    name: "Zero Hunger",
    img: "/goals/goal2.png",
    color: "background-color: #dda73a;",
    link: "https://globalgoals.org/goals/2-zero-hunger/",
  },
  {
    number: 3,
    name: "Good Health and Well-being",
    img: "/goals/goal3.png",
    color: "background-color: #4c9f38;",
    link: "https://globalgoals.org/goals/3-good-health-and-well-being/",
  },
  {
    number: 4,
    name: "Quality Education",
    img: "/goals/goal4.png",
    color: "background-color: #c7212f;",
    link: "https://globalgoals.org/goals/4-quality-education/",
  },
  {
    number: 5,
    name: "Gender Equality",
    img: "/goals/goal5.png",
    color: "background-color: #ff3a21;",
    link: "https://globalgoals.org/goals/5-gender-equality/",
  },
  {
    number: 6,
    name: "Clean water and Sanitation",
    img: "/goals/goal6.png",
    color: "background-color: #26bde2;",
    link: "https://globalgoals.org/goals/6-clean-water-and-sanitation/",
  },
  {
    number: 7,
    name: "Affordable and clean energy",
    img: "/goals/goal7.png",
    color: "background-color: #fcc30b;",
    link: "https://globalgoals.org/goals/7-affordable-and-clean-energy/",
  },
  {
    number: 8,
    name: "Decent Work and Economic growth",
    img: "/goals/goal8.png",
    color: "background-color: #a21942;",
    link: "https://globalgoals.org/goals/8-decent-work-and-economic-growth/",
  },
  {
    number: 9,
    name: "Industry, innovation and infrastructure",
    img: "/goals/goal9.png",
    color: "background-color: #fd6925;",
    link: "https://globalgoals.org/goals/9-industry-innovation-and-infrastructure/",
  },
  {
    number: 10,
    name: "Reduced Inequalities",
    img: "/goals/goal10.png",
    color: "background-color: #dd1367;",
    link: "https://globalgoals.org/goals/10-reduced-inequalities/",
  },
  {
    number: 11,
    name: "Sustainable cities and communities",
    img: "/goals/goal11.png",
    color: "background-color: #fd9d24;",
    link: "https://globalgoals.org/goals/11-sustainable-cities-and-communities/",
  },
  {
    number: 12,
    name: "Responsible consumption and prduction",
    img: "/goals/goal12.png",
    color: "background-color: #cd8b2a;",
    link: "https://globalgoals.org/goals/12-responsible-consumption-and-production/",
  },
  {
    number: 13,
    name: "Climate action",
    img: "/goals/goal13.png",
    color: "background-color: #3f7e44;",
    link: "https://globalgoals.org/goals/13-climate-action/",
  },
  {
    number: 14,
    name: "Life below water",
    img: "/goals/goal14.png",
    color: "background-color: #0a97d9;",
    link: "https://globalgoals.org/goals/14-life-below-water/",
  },
  {
    number: 15,
    name: "Life on land",
    img: "/goals/goal15.png",
    color: "background-color: #56c02b;",
    link: "https://globalgoals.org/goals/15-life-on-land/",
  },
  {
    number: 16,
    name: "Peace, justice and strong institutions",
    img: "/goals/goal16.png",
    color: "background-color: #015591;",
    link: "https://globalgoals.org/goals/16-peace-justice-and-strong-institutions/",
  },
  {
    number: 17,
    name: "Partnership for the goals",
    img: "/goals/goal17.png",
    color: "background-color: #0f376b;",
    link: "https://globalgoals.org/goals/17-partnerships-for-the-goals/",
  },
];

onMounted(() => {
  ctx = gsap.context(() => {
    
    const sdgBoxes = gsap.utils.toArray(".sdg-box"); 
    const allItems = [...sdgBoxes, ".global-goals-link"]; 

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
      duration: 0.7,
      ease: "power2.out",
    })
    .from(allItems, {
      y: 50,
      opacity: 0,
      duration: 0.4,
      stagger: 0.05,
      ease: "power1.out",
    }, "-=0.3");
    
  }, mainSection.value); 
});

onUnmounted(() => {
  ctx.revert();
});
</script>

<style lang="scss">
#sdgs {
  padding: 15px;
  .heading {
    text-align: center;
    h2 {
      margin-bottom: 15px;
      font-weight: 900;
      font-size: 25px;
      color: var(--primary);
    }
  }

  .content {
    margin-top: 25px;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-auto-rows: auto;
    gap: 15px;
    .box {
      position: relative;
      aspect-ratio: 1/1;
      padding: 5px;
      display: flex;
      flex-direction: column;
      gap: 15px;
      overflow: hidden;
      cursor: pointer;
      &::before {
        content: "";
        position: absolute;
        top: -100%;
        left: -100%;
        width: 200%;
        height: 200%;
        background: linear-gradient(
          120deg,
          rgba(255, 255, 255, 0) 30%,
          rgba(255, 255, 255, 0.4) 50%,
          rgba(255, 255, 255, 0) 100%
        );
        transform: translateX(-100%);
        transition: transform 0.8s ease;
        pointer-events: none;
      }
      &:hover::before {
        transform: translateX(100%);
      }
      .text {
        display: flex;
        gap: 10px;
        text-transform: uppercase;
        font-weight: 900;
        font-size: 12.5px;
        color: #fff;
      }
      img {
        width: 100%;
        height: 60%;
        object-fit: contain;
      }
    }
    .sdg {
      padding: 5px;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      gap: 15px;
      img {
        width: 100%;
        height: 50%;
        object-fit: contain;
      }
      p {
        text-transform: uppercase;
        font-weight: 900;
        font-size: 12.5px;
      }
    }
  }
}

@media (min-width: 600px) and (max-width: 1279px) {
  #sdgs {
    padding: 25px;
    .content {
      grid-template-columns: repeat(3, 1fr);
      gap: 25px;
      .box {
        padding: 10px;
        .text {
          font-size: 15px;
        }
      }
    }
  }
}

@media (min-width: 1280px) {
  #sdgs {
    padding: 25px 100px;
    .heading {
      h2 {
        font-size: 35px;
      }
    }
    .content {
      grid-template-columns: repeat(6, 1fr);
      gap: 15px;
      :nth-child(3),
      :nth-child(6),
      :nth-child(7),
      :nth-child(8),
      :nth-child(9),
      :nth-child(12) {
        aspect-ratio: unset;
        grid-column: span 2;
        img {
          margin: auto;
          width: 50%;
        }
      }
      .box {
        padding: 10px;
        .text {
          font-size: 15px;
        }
      }
    }
  }
}
</style>