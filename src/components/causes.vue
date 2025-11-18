<template>
  <section id="causes" ref="mainSection">
    <div class="heading">
      <h2>The Main Drivers of Climate Change</h2>
    </div>

    <div class="grid">
      <div v-for="(item, index) in causes" :key="index" class="card">
        <img :src="item.img" :alt="item.name" /> 
        <div class="text">
          <h3>{{ item.name }}</h3>
          <p @click="toggleText(index)" :class="{ show: expandedItems[index] }">
            {{ item.info }}
          </p>
        </div>
      </div>
    </div>

    <div class="footer-cta">
      <p>
        These human-driven forces are rewriting our planet’s future — but
        understanding them is the first step toward reversing the damage.
      </p>
      <a href="#solutions">
        <CTA label="See Solutions" />
      </a>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";
import CTA from "./cta.vue";

import gsap from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);

const mainSection = ref(null); // Ref for the main section element
let ctx;

const causes = [
  {
    name: "Burning Fossil Fuels",
    info: "Power plants, vehicles, and industries rely heavily on coal, oil, and gas — releasing billions of tons of carbon dioxide (CO₂) into the atmosphere every year. This is the single largest driver of global warming.",
    img: "/causes/fossils.jpg",
  },
  {
    name: "Deforestation",
    info: "Forests act as the planet’s lungs, absorbing CO₂. When we cut them down for agriculture, timber, or urban expansion, not only do we lose carbon sinks — the burning and decay of trees also release stored carbon back into the air.",
    img: "/causes/deforestation.jpg",
  },
  {
    name: "Industrial Emissions",
    info: "Factories and manufacturing facilities emit massive amounts of greenhouse gases, including methane (CH₄) and nitrous oxide (N₂O), from chemical processes, cement production, and waste management.",
    img: "/causes/emission.jpg",
  },
  {
    name: "Agriculture & Livestock",
    info: "Cattle and rice farming produce large volumes of methane, a gas far more potent than CO₂ in trapping heat. Fertilizer use also releases nitrous oxide, adding to the warming effect.",
    img: "/causes/agriculture.jpg",
  },
  {
    name: "Transportation",
    info: "Cars, planes, ships, and trucks powered by fossil fuels produce a staggering share of CO₂ emissions, with global transport accounting for nearly one-quarter of energy-related emissions.",
    img: "/causes/transportation.jpg",
  },
  {
    name: "Waste & Landfills",
    info: "Organic waste decomposing in landfills emits methane. Meanwhile, plastics and synthetic materials contribute to emissions through both production and degradation.",
    img: "/causes/waste.jpg",
  },
];

const expandedItems = ref(Array(causes.length).fill(false));

const toggleText = (index) => {
  expandedItems.value[index] = !expandedItems.value[index];
};

onMounted(() => {
  ctx = gsap.context(() => {
    const tl = gsap.timeline({
      scrollTrigger: {
        trigger: mainSection.value,
        start: "top 75%", 
        toggleActions: "play none none reverse",
      },
    });

    tl.from(".heading", {
      y: 50,
      opacity: 0,
      duration: 0.8,
      ease: "power3.out",
    })
    .from(".card", {
      y: 60,
      opacity: 0,
      duration: 0.7,
      stagger: 0.1,
      ease: "power2.out",
    }, "-=0.4") 
    .from(".footer-cta", {
      y: 30,
      opacity: 0,
      duration: 0.6,
      ease: "power2.out",
    }, "-=0.3");

  }, mainSection.value);
});

onUnmounted(() => {
  ctx.revert();
});
</script>

<style lang="scss">
#causes {
  padding: 15px;
  display: flex;
  flex-direction: column;
  gap: 25px;
  .heading {
    text-align: center;
    h2 {
      font-weight: 900;
      font-size: 25px;
      color: var(--primary);
    }
  }

  .grid {
    display: grid;
    grid-template-columns: repeat(1, 1fr);
    gap: 25px;
    .card {
      position: relative;
      width: 100%;
      height: 400px;
      border-radius: 16px;
      overflow: hidden;
      .text {
        position: absolute;
        top: 0;
        left: 0;
        padding: 15px;
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        justify-content: end;
        background: #00000050;
        color: #f7f7f7;
        h3 {
          margin-bottom: 5px;
          font-weight: bold;
          font-size: 25px;
        }
        p {
          display: -webkit-box;
          -webkit-box-orient: vertical;
          -webkit-line-clamp: 3;
          text-overflow: ellipsis;
          padding-right: 15px;
          font-size: 12.5px;
          overflow: hidden;
          cursor: pointer;
          transition: 0.3s;
          &.show {
            display: block;
            -webkit-line-clamp: unset;
            overflow: visible;
          }
        }
      }
      img {
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }
  }
  .footer-cta {
    display: flex;
    flex-direction: column;
    align-items: start;
    gap: 15px;
  }
}

@media (min-width: 600px) and (max-width: 1279px) {
  #causes {
    margin: 25px 0;
    padding: 25px;
    .heading {
      h2 {
        margin: 0 auto;
        max-width: 500px;
        font-size: 35px;
      }
    }
    .grid {
      grid-template-columns: repeat(8, 1fr);
      gap: 15px;
      > :nth-child(1) {
        grid-column: span 5;
      }
      > :nth-child(2) {
        grid-column: span 3;
      }
      > :nth-child(3) {
        grid-column: span 4;
      }
      > :nth-child(4) {
        grid-column: span 4;
      }
      > :nth-child(5) {
        grid-column: span 3;
      }
      > :nth-child(6) {
        grid-column: span 5;
      }
    }
    .footer-cta {
      max-width: 600px;
    }
  }
}
@media (min-width: 1280px) {
  #causes {
    padding: 50px;
    .heading {
      h2 {
        margin: 0 auto;
        max-width: 500px;
        font-size: 35px;
      }
    }
    .grid {
      grid-template-columns: repeat(18, 1fr);
      gap: 15px;
      > :nth-child(1) {
        grid-column: span 7;
      }
      > :nth-child(2) {
        grid-column: span 4;
      }
      > :nth-child(3) {
        grid-column: span 7;
      }
      > :nth-child(4) {
        grid-column: span 6;
      }
      > :nth-child(5) {
        grid-column: span 4;
        order: 1;
      }
      > :nth-child(6) {
        grid-column: span 8;
      }
    }
    .footer-cta {
      max-width: 800px;
    }
  }
}
</style>