<template>
  <section id="solutions" ref="mainSection">
    <div class="heading">
      <h2>The Path to a Cooler Planet</h2>
      <p>A cooler future is possible—if we act with purpose today.</p>
    </div>

    <div class="grid">
      <div v-for="(item, index) in solutions" :key="index" class="card">
        <div class="top">
          <div class="circle">
            <component :is="item.icon" :size="24" />
          </div>
          <h3>{{ item.title }}</h3>
        </div>
        <p>{{ item.info }}</p>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";
import {
  PhBicycle,
  PhGlobeHemisphereEast,
  PhPlant,
  PhRecycle,
  PhSolarPanel,
  PhTree,
} from "@phosphor-icons/vue";

import gsap from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);

const mainSection = ref(null);
let ctx;

const solutions = [
  {
    icon: PhSolarPanel,
    title: "Shift to Renewable Energy",
    info: "Replace coal and oil with solar, wind, hydro, and geothermal power. Clean energy reduces emissions and also powers sustainable growth.",
  },
  {
    icon: PhTree,
    title: "Reforest & Protect Nature",
    info: "Planting trees, restoring wetlands, and preserving forests can absorb tons of CO₂ while protecting biodiversity and natural habitats.",
  },
  {
    icon: PhRecycle,
    title: "Reinvent Waste Management",
    info: "Reduce, reuse, and recycle. Compost organic waste, eliminate single-use plastics, and design materials that return safely to the environment.",
  },
  {
    icon: PhPlant,
    title: "Transform Agriculture",
    info: "Support regenerative farming, plant-based diets, and methane-reducing livestock systems. Sustainable food systems protect the planet.",
  },
  {
    icon: PhBicycle,
    title: "Rethink Transportation",
    info: "Choose electric vehicles, public transport, walking, or biking. Encourage cities to invest in low-carbon transit and green infrastructure.",
  },
  {
    icon: PhGlobeHemisphereEast,
    title: "Empower Climate Action",
    info: "Educate communities, vote for climate-conscious leaders, and support global green initiatives. Individual action fuels mutual change.",
  },
];

onMounted(() => {
  ctx = gsap.context(() => {
    const cards = gsap.utils.toArray(".card");

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
    });
    const startState = {
      y: 80,
      opacity: 0,
      rotationZ: 10,
    };
    const endState = {
      y: 0,
      opacity: 1,
      rotationZ: 0,
      duration: 0.8,
      stagger: 0.1,
      ease: "back.out(1.2)",
    };

    tl.fromTo(cards, startState, endState, "-=0.3");
  }, mainSection.value);
});

onUnmounted(() => {
  ctx.revert();
});
</script>

<style lang="scss">
#solutions {
  margin: 25px 0;
  padding: 25px 15px;
  background: var(--primary);
  overflow-x: hidden;

  .heading {
    padding: 0 15px;
    text-align: center;
    color: #f7f7f7;
    h2 {
      font-weight: 900;
      font-size: 25px;
    }
    p {
      margin-top: 15px;
    }
  }

  .grid {
    margin-top: 25px;
    display: grid;
    grid-template-columns: repeat(1, 1fr);
    gap: 25px;
    .card {
      padding: 25px;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      gap: 25px;
      background: var(--accent);
      border-radius: 16px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2),
        0 8px 16px rgba(62, 126, 69, 0.35),
        inset 0 0 8px rgba(255, 255, 255, 0.1);
      transition: 0.3s ease;
      &:hover {
        transform: translateY(-2.5px);
        box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3),
          0 0 15px rgba(236, 249, 110, 0.4);
      }
      .top {
        .circle {
          width: 48px;
          height: 48px;
          display: flex;
          justify-content: center;
          align-items: center;
          background: var(--primary);
          color: #f7f7f7;
          border-radius: 50%;
        }
        h3 {
          margin-top: 15px;
          font-weight: bold;
          font-size: 20px;
          color: var(--primary);
        }
      }
    }
  }
}

@media (min-width: 600px) and (max-width: 1023px) {
  #solutions {
    padding: 25px;
    .heading {
      margin: 0 auto;
      max-width: 600px;
      h2 {
        font-size: 35px;
      }
    }
    .grid {
      grid-template-columns: repeat(2, 1fr);
    }
  }
}

@media (min-width: 1024px) {
  #solutions {
    padding: 100px;
    .heading {
      margin: 0 auto;
      max-width: 600px;
      h2 {
        font-size: 35px;
      }
    }
    .grid {
      grid-template-columns: repeat(3, 1fr);
    }
  }
}
</style>