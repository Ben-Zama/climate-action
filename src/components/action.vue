<template>
  <section id="action" ref="mainSection">
    <div class="heading">
      <h2>Take Action Now</h2>
      <p>
        Small changes create massive impact. Start your sustainability journey
        today.
      </p>
    </div>

    <div class="container">
      <div div class="highlights">
        <div class="grid highlights-grid">
          <div
            v-for="(action, index) in actionHighlights"
            :key="index"
            class="card highlight-card"
          >
            <component :is="action.icon" weight="bold" class="highlight-icon" />
            <h3>{{ action.title }}</h3>
            <p>{{ action.description }}</p>
          </div>
        </div>
        <div class="search-box">
          <h3>
            <ph-map-pin :size="28" weight="duotone" /> Find Recycling Centers
            Near You
          </h3>
          <div class="search-row">
            <div class="input-wrap">
              <ph-magnifying-glass class="search-icon" />
              <input
                type="text"
                v-model="location"
                placeholder="Enter your location"
                @keydown.enter="handleSearch"
              />
            </div>
            <button class="btn" @click="handleSearch">
              <CTA label="Search" />
            </button>
          </div>
        </div>
      </div>

      <div class="pledge-form">
        <h3>Make Your Pledge</h3>
        <p>
          Select the actions you commit to – see your impact grow in real-time.
        </p>

        <div class="grid pledge-grid">
          <div
            v-for="action in pledgeActions"
            :key="action.id"
            :class="[
              'pledge-card',
              { active: selectedPledges.includes(action.id) },
            ]"
            @click="togglePledge(action.id)"
          >
            <input
              type="checkbox"
              :id="action.id"
              :checked="selectedPledges.includes(action.id)"
            />
            <label :for="action.id">
              <component :is="action.icon" :size="20" weight="bold" />
              {{ action.label }}
            </label>
            <small>
              Annual Impact:
              <span>{{ action.wasteKg }}kg waste</span>
              <span v-if="action.co2Kg > 0">, {{ action.co2Kg }}kg CO₂</span>
            </small>
          </div>
        </div>

        <div class="impact">
          <h4>Your Annual Impact</h4>
          <div class="impact-grid">
            <div>
              <strong>{{ totalImpact.waste.toFixed(1) }}kg</strong>
              <p>Waste Prevented</p>
            </div>
            <div>
              <strong>{{ totalImpact.co2.toFixed(1) }}kg</strong>
              <p>CO₂ Prevented</p>
            </div>
          </div>
        </div>

        <button
          class="btn"
          :disabled="!selectedPledges.length"
          @click="showPledgeCard = true"
        >
          <CTA label="Take The Pledge" />
        </button>
      </div>
    </div>

    <div class="footer">
      <h2 class="headline">Together, we can turn the tide on waste.</h2>
      <p>Share your pledge with friends and family to multiply your impact</p>
    </div>

    <dialog
      @click.self="showPledgeCard = false"
      v-if="showPledgeCard"
      open
      class="pledge-dialog"
    >
      <div class="dialog-content">
        <div class="dialog-icon">
          <img src="/logo.png" alt="" />
        </div>
        <h3>Climate Action Pledge</h3>
        <p>I commit to these sustainable actions:</p>
        <ul>
          <li
            v-for="action in pledgeActions.filter((a) =>
              selectedPledges.includes(a.id)
            )"
            :key="action.id"
          >
            <component :is="action.icon" :size="20" weight="duotone" />
            <p>{{ action.label }}</p>
          </li>
        </ul>

        <div class="impact">
          <h4>My Annual Impact</h4>
          <div class="impact-grid">
            <div>
              <strong>{{ totalImpact.waste.toFixed(1) }}kg</strong>
              <p>Waste Prevented</p>
            </div>
            <div>
              <strong>{{ totalImpact.co2.toFixed(1) }}kg</strong>
              <p>CO₂ Prevented</p>
            </div>
          </div>
        </div>

        <p class="quote">
          “Small actions, when multiplied by millions of people, can transform
          the world.”
        </p>
        <button class="btn close" @click="showPledgeCard = false">
          <CTA label="Close" />
        </button>
      </div>
    </dialog>
  </section>
</template>

<script setup>
import { ref, computed, onMounted, onUnmounted } from "vue";
import {
  PhMapPin,
  PhMagnifyingGlass,
  PhRecycle,
  PhDrop,
  PhShoppingBag,
  PhForkKnife,
  PhCoffee,
  PhLightning,
  PhTree,
  PhLeaf,
} from "@phosphor-icons/vue";
import CTA from "./cta.vue";

import gsap from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);

const mainSection = ref(null);
let ctx;

const location = ref("");
const userCity = ref("your city");
const selectedPledges = ref([]);
const showPledgeCard = ref(false);

const pledgeActions = [
  {
    id: "bottles",
    label: "Use reusable water bottles",
    wasteKg: 14.6,
    co2Kg: 35.0,
    icon: PhDrop,
  },
  {
    id: "bags",
    label: "Bring reusable shopping bags",
    wasteKg: 8.8,
    co2Kg: 18.0,
    icon: PhShoppingBag,
  },
  {
    id: "straws",
    label: "Refuse single-use straws",
    wasteKg: 2.2,
    co2Kg: 4.5,
    icon: PhForkKnife,
  },
  {
    id: "coffee",
    label: "Use reusable coffee cups",
    wasteKg: 11.0,
    co2Kg: 22.0,
    icon: PhCoffee,
  },
  {
    id: "composting",
    label: "Start composting food waste",
    wasteKg: 182.5,
    co2Kg: 320.0,
    icon: PhLeaf,
  },
  {
    id: "energy",
    label: "Switch to renewable energy",
    wasteKg: 0,
    co2Kg: 2200.0,
    icon: PhLightning,
  },
];

const actionHighlights = [
  {
    icon: PhRecycle,
    title: "Recycle Right",
    description: "Learn what can be recycled in your area",
  },
  {
    icon: PhShoppingBag,
    title: "Refuse Single-Use",
    description: "Choose reusable alternatives",
  },
  {
    icon: PhTree,
    title: "Compost Organic Waste",
    description: "Turn food scraps into nutrients",
  },
  {
    icon: PhDrop,
    title: "Reduce Water Waste",
    description: "Every drop counts for our planet",
  },
];

onMounted(() => {
  if ("geolocation" in navigator) {
    navigator.geolocation.getCurrentPosition(() => {
      userCity.value = "your area";
    });
  }

  ctx = gsap.context(() => {
    const tl = gsap.timeline({
      scrollTrigger: {
        trigger: mainSection.value,
        start: "top 75%",
        end: "bottom bottom",
        toggleActions: "play none none reverse",
      },
    });

    tl.from(".heading", {
      y: 30,
      opacity: 0,
      duration: 0.6,
      ease: "power2.out",
    })

      .fromTo(
        ".highlight-card",
        {
          opacity: 0,
          scale: 0.8,
          duration: 0.5,
          stagger: 0.1,
          ease: "power1.out",
        },
        {
          opacity: 1,
          scale: 1,
        },
        "-=0.3"
      )
      .from(
        ".search-box",
        {
          y: 30,
          opacity: 0,
          duration: 0.6,
          ease: "power2.out",
        },
        "<0.1"
      )
      .from(
        ".pledge-form",
        {
          x: 50,
          opacity: 0,
          duration: 0.7,
          ease: "power2.out",
        },
        "<0.1"
      )

      .fromTo(
        ".pledge-card",
        {
          scale: 0.9,
          opacity: 0,
          duration: 0.4,
          stagger: 0.05,
          ease: "back.out(1.7)",
        },
        {
          scale: 1,
          opacity: 1,
        },
        "<0.3"
      )
      .from(
        ".footer",
        {
          y: 30,
          opacity: 0,
          duration: 0.6,
          ease: "power2.out",
        },
        "-=0.5"
      );
  }, mainSection.value);
});

onUnmounted(() => {
  ctx.revert();
});

const handleSearch = () => {
  const searchQuery = location.value || userCity.value;
  // This link will be replaced with a functional search engine link in a real app
  window.open(
    `https://www.google.com/maps/search/recycling+center+near+${encodeURIComponent(
      searchQuery
    )}`,
    "_blank"
  );
};

const togglePledge = (id) => {
  selectedPledges.value = selectedPledges.value.includes(id)
    ? selectedPledges.value.filter((p) => p !== id)
    : [...selectedPledges.value, id];
};

const totalImpact = computed(() =>
  pledgeActions
    .filter((a) => selectedPledges.value.includes(a.id))
    .reduce(
      (acc, a) => ({ waste: acc.waste + a.wasteKg, co2: acc.co2 + a.co2Kg }),
      { waste: 0, co2: 0 }
    )
);
</script>

<style lang="scss">
#action {
  padding: 15px;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 25px;

  .heading {
    text-align: center;
    h2 {
      margin-bottom: 15px;
      font-size: 25px;
      font-weight: 900;
      color: var(--primary);
    }
  }

  .container {
    display: flex;
    flex-direction: column;
    gap: 25px;
    width: 100%;

    .highlights {
      .highlights-grid {
        width: 100%;
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        gap: 15px;
        .highlight-card {
          padding: 15px;
          display: flex;
          flex-direction: column;
          align-items: center;
          gap: 15px;
          text-align: center;
          border: 1px solid #e5e7eb;
          border-radius: 8px;
          transition: all 0.3s;
          &:hover {
            border-color: var(--primary);
            box-shadow: 0 0 20px rgba(34, 197, 94, 0.2);
          }
          .highlight-icon {
            font-size: 2.5rem;
            color: var(--primary);
          }
          h3 {
            font-size: 15px;
            font-weight: 900;
          }
          p {
            font-size: 12.5px;
          }
        }
      }
    }

    .search-box {
      margin-top: 25px;
      padding: 15px;
      border: 1px solid #e5e7eb;
      border-radius: 16px;
      h3 {
        display: flex;
        align-items: center;
        gap: 15px;
        font-weight: bold;
        svg {
          color: var(--primary);
        }
      }

      .search-row {
        margin-top: 15px;
        display: flex;
        flex-direction: column;
        gap: 15px;
        .input-wrap {
          position: relative;
          flex: 1;
          .search-icon {
            position: absolute;
            left: 1rem;
            top: 50%;
            transform: translateY(-50%);
            color: #9ca3af;
          }
          input {
            width: 100%;
            padding: 0.75rem 1rem 0.75rem 2.5rem;
            border: 1px solid #d1d5db;
            border-radius: 16px;
            font-size: 1rem;
            &:hover,
            &:focus {
              outline: 1px solid var(--primary);
            }
          }
        }
        .btn {
          button {
            padding: 10px 0;
            width: 100%;
            &:hover {
              transform: scale(1);
            }
          }
        }
      }
    }

    .pledge-form {
      padding: 15px;
      text-align: center;
      background: #f9f9ff;
      border: 1px solid #e5e7eb;
      border-radius: 8px;
      > h3 {
        font-weight: bold;
        font-size: 20px;
        color: var(--primary);
      }
      > p {
        font-size: 15px;
        opacity: 0.75;
      }

      .pledge-grid {
        margin-top: 15px;
        display: grid;
        gap: 15px;
        .pledge-card {
          position: relative;
          padding: 15px;
          display: flex;
          flex-direction: column;
          gap: 7.5px;
          text-align: left;
          border: 1px solid #e5e7eb;
          border-radius: 8px;
          transition: all 0.3s;
          z-index: 2;
          cursor: pointer;
          &:hover {
            box-shadow: 0 0 15px rgba(34, 197, 94, 0.1);
          }
          &.active {
            border-color: var(--primary);
            box-shadow: 0 0 15px rgba(34, 197, 94, 0.2);
          }
          input {
            accent-color: var(--primary);
            width: 16px;
            height: 16px;
            display: none;
          }
          label {
            width: max-content;
            display: flex;
            align-items: center;
            gap: 10px;
            font-weight: bold;
          }
          small {
            display: block;
          }
        }
      }

      .impact {
        margin-top: 15px;
        background: linear-gradient(
          to right,
          rgb(62, 126, 69, 0.1),
          rgb(206, 206, 206, 0.2),
          rgb(236, 249, 110, 0.1)
        );
        border: 1px solid rgba(34, 197, 94, 0.3);
        border-radius: 8px;
        padding: 15px;
        margin-bottom: 15px;

        h4 {
          margin-bottom: 15px;
        }

        .impact-grid {
          display: grid;
          grid-template-columns: repeat(2, 1fr);
          text-align: center;

          strong {
            font-size: 1.5rem;
            color: var(--primary);
          }
        }
      }

      .btn {
        width: 100%;
        &:disabled {
          opacity: 0.6;
          cursor: not-allowed;
          user-select: none;
        }
        button {
          padding: 10px 0;
          width: 100%;
          &:hover {
            transform: scale(1);
          }
        }
      }
    }
  }

  .footer {
    text-align: center;
    .headline {
      margin-bottom: 15px;
      font-weight: 900;
      font-size: 25px;
      color: var(--primary);
    }
  }

  .pledge-dialog {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;
    background: rgba(0, 0, 0, 0.5);
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 5;
    cursor: pointer;
    .dialog-content {
      padding: 15px;
      max-width: 500px;
      width: 90%;
      max-height: 90vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 15px;
      text-align: center;
      background: #fff;
      border-radius: 16px;
      overflow-y: scroll;
      cursor: auto;
      .dialog-icon {
        width: 20%;
        img {
          width: 100%;
          height: 100%;
          object-fit: contain;
        }
      }
      h3 {
        font-weight: 900;
        font-size: 20px;
        color: var(--primary);
      }
      ul {
        list-style: none;
        width: 100%;
        display: flex;
        flex-direction: column;
        gap: 15px;
        li {
          padding: 15px;
          display: flex;
          align-items: center;
          gap: 15px;
          text-align: start;
          border: 1px solid #d1d5db;
          border-radius: 16px;
          svg {
            color: var(--primary);
          }
        }
      }
      .impact {
        h4 {
          font-weight: bold;
        }
        .impact-grid {
          display: flex;
          flex-direction: column;
          gap: 5px;
          strong {
            font-size: 25px;
            color: var(--primary);
            font-weight: 900;
          }
        }
      }
      .quote {
        color: #6b7280;
        font-style: italic;
      }
      .close {
        width: 50%;
        button {
          padding: 10px 0;
          width: 100%;
        }
      }
    }
  }
}

@media (min-width: 600px) and (max-width: 1279px) {
  #action {
    padding: 25px;
    .container {
      .pledge-form {
        .pledge-grid {
          grid-template-columns: repeat(2, 1fr);
        }
      }
    }
    .pledge-dialog {
      .dialog-content {
        ul {
          display: grid;
          grid-template-columns: repeat(2, 1fr);
          li {
            svg {
              width: 32px;
            }
          }
        }
        .impact {
          .impact-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 25px;
          }
        }
      }
    }
  }
}

@media (min-width: 1280px) {
  #action {
    padding: 50px;
    .heading {
      h2 {
        font-size: 35px;
      }
    }
    .container {
      flex-direction: row;
      align-items: flex-start; 
      gap: 50px;
      max-width: 1200px; 
      .highlights {
        width: 45%;
      }
      .pledge-form {
        width: 55%;
        .pledge-grid {
          grid-template-columns: repeat(2, 1fr);
        }
      }
    }
    .pledge-dialog {
      .dialog-content {
        ul {
          display: grid;
          grid-template-columns: repeat(2, 1fr);
          li {
            svg {
              width: 32px;
            }
          }
        }
        .impact {
          .impact-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 25px;
          }
        }
      }
    }
  }
}
</style>
