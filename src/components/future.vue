<template>
  <section id="future" ref="mainSection">
    <div class="heading">
      <h2>Our Planet in Peril</h2>
      <p>
        These projections show what happens if we continue on our current path
        without significant action
      </p>
    </div>

    <div class="bento-grid">
      <div class="card">
        <h3>
          <PhThermometerHot :size="24" class="text-red-500" /> Global
          Temperature Rise
        </h3>
        <p>
          Average global temperatures are climbing faster than ever, pushing
          ecosystems to the brink.
        </p>
        <apexchart
          type="area"
          height="300"
          :options="temperature.options"
          :series="temperature.series"
        />
        <p>
          By <strong>2080</strong>, global temperatures could soar up to
          <strong>5°C</strong> above pre-industrial levels — triggering
          irreversible melting, droughts, and mass species extinction.
        </p>
      </div>

      <div class="card">
        <h3><PhWaves :size="24" class="text-blue-400" /> Sea-Level Rise</h3>
        <p>
          Melting ice caps and thermal expansion are steadily lifting our seas
          higher each year.
        </p>
        <apexchart
          type="area"
          height="300"
          :options="seaLevel.options"
          :series="seaLevel.series"
        />
        <p>
          By <strong>2080</strong>, sea levels could rise by
          <strong>over a meter</strong>, displacing hundreds of millions and
          swallowing coastal cities worldwide.
        </p>
      </div>

      <div class="card">
        <h3>
          <PhOrange :size="24" class="text-orange-400" /> Crop Yield Decline
        </h3>
        <p>
          Extreme heat and erratic rainfall are undermining global food
          security.
        </p>
        <apexchart
          type="bar"
          height="300"
          :options="crop.options"
          :series="crop.series"
        />
        <p>
          Agricultural productivity could drop by <strong>over 70%</strong> in
          key regions by 2080, leading to mass hunger and economic instability.
        </p>
      </div>

      <div class="card">
        <h3>
          <PhSnowflake :size="24" class="text-blue-300" /> Glacial Ice Lost
        </h3>
        <p>
          Glaciers — Earth’s natural water reservoirs — are disappearing at an
          alarming rate.
        </p>
        <apexchart
          type="area"
          height="300"
          :options="glacial.options"
          :series="glacial.series"
        />
        <p>
          By <strong>2080</strong>, we could lose up to
          <strong>95% of glacial ice</strong>, cutting off freshwater to
          billions and accelerating sea-level rise.
        </p>
      </div>

      <div class="card">
        <h3>
          <PhCloudLightning :size="24" class="text-purple-700" /> Extreme
          Weather Events
        </h3>
        <p>
          Unchecked warming fuels an explosion of violent weather across the
          planet.
        </p>
        <apexchart
          type="bar"
          height="300"
          :options="weather.options"
          :series="weather.series"
        />
        <p>
          By <strong>2080</strong>, the number of major climate disasters —
          hurricanes, wildfires, and floods — could increase
          <strong>eightfold</strong>, devastating communities and economies.
        </p>
      </div>
    </div>

    <div class="footer-cta">
      <p>
        But it doesn’t have to end this way. Every act — recycling, reducing
        waste, switching to renewables — matters. Together, we can rewrite this
        future.
      </p>
      <a href="#action">
        <CTA label="Take Action" />
      </a>
    </div>
  </section>
</template>

<script setup>
import { onMounted, onUnmounted, ref } from "vue";
import CTA from "./cta.vue";
import {
  PhCloudLightning,
  PhOrange,
  PhSnowflake,
  PhThermometerHot,
  PhWaves,
} from "@phosphor-icons/vue";

import gsap from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);

const mainSection = ref(null);

const years = ["2020", "2030", "2040", "2050", "2060", "2070", "2080"];

const baseOptions = {
  chart: {
    toolbar: { show: false },
    background: "transparent",
    zoom: { enabled: false },
  },
  dataLabels: { enabled: false },
  stroke: { curve: "smooth", width: 3 },
  grid: {
    borderColor: "rgba(255,255,255,0.1)",
    row: { colors: ["#cecece", "transparent"], opacity: 0.05 },
    column: { colors: ["#cecece", "transparent"], opacity: 0.05 },
  },
  xaxis: { categories: years, labels: { style: { colors: "#aaa" } } },
  yaxis: { labels: { style: { colors: "#aaa" } } },
  tooltip: { theme: "dark", style: { fontSize: "13px" } },
};

const temperature = {
  series: [
    { name: "Temperature (°C)", data: [1.2, 1.5, 2.0, 2.7, 3.5, 4.2, 5.0] },
  ],
  options: {
    ...baseOptions,
    colors: ["#fb2c63"],
    fill: { type: "gradient", gradient: { opacityFrom: 0.5, opacityTo: 0.2 } },
  },
};

const seaLevel = {
  series: [{ name: "Sea Level (cm)", data: [20, 28, 40, 55, 75, 100, 130] }],
  options: {
    ...baseOptions,
    colors: ["#51a2ff"],
    fill: { gradient: { opacityFrom: 0.5, opacityTo: 0.2 } },
  },
};

const glacial = {
  series: [{ name: "Ice Lost (%)", data: [15, 25, 38, 52, 68, 82, 95] }],
  options: {
    ...baseOptions,
    colors: ["#8ec5ff"],
    fill: { gradient: { opacityFrom: 0.5, opacityTo: 0.2 } },
  },
};

const crop = {
  series: [{ name: "Decline (%)", data: [5, 12, 22, 35, 48, 60, 75] }],
  options: {
    ...baseOptions,
    colors: ["#ff8904"],
    plotOptions: { bar: { borderRadius: 2.5, columnWidth: "50%" } },
  },
};

const weather = {
  series: [{ name: "Major Events", data: [22, 35, 52, 75, 105, 140, 185] }],
  options: {
    ...baseOptions,
    colors: ["#8200db"],
    plotOptions: { bar: { borderRadius: 2.5, columnWidth: "50%" } },
  },
};

let ctx;

onMounted(() => {
  ctx = gsap.context(() => {
    const tl = gsap.timeline({
      scrollTrigger: {
        trigger: mainSection.value,
        start: "top 75%",
        end: "bottom 20%",
        toggleActions: "play none none reverse",
      },
    });

    tl.from(".heading", {
      y: 50,
      opacity: 0,
      duration: 0.8,
      ease: "power3.out",
    })
      .from(
        ".card",
        {
          y: 60,
          opacity: 0,
          duration: 0.8,
          stagger: 0.15,
          ease: "back.out(1.2)",
        },
        "-=0.4"
      )

      .from(
        ".footer-cta",
        {
          y: 30,
          opacity: 0,
          duration: 0.6,
          ease: "power2.out",
        },
        "-=0.2"
      );
  }, mainSection.value);
});

onUnmounted(() => {
  ctx.revert();
});
</script>

<style lang="scss">
#future {
  margin: 25px 0;
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
    p {
      opacity: 0.8;
    }
  }

  .bento-grid {
    display: grid;
    grid-template-columns: repeat(1, 1fr);
    gap: 25px;

    .card {
      padding: 15px;
      border: 1px solid #ceceff50;
      border-radius: 8px;
      background: #ceceff20;

      h3 {
        display: flex;
        align-items: center;
        gap: 15px;
        font-size: 20px;
        font-weight: bold;
        color: var(--primary);
      }

      p {
        opacity: 0.8;
        font-size: 12.5px;
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
  #future {
    padding: 25px;
    .heading {
      h2 {
        font-size: 35px;
      }
      p {
        margin: 0 auto;
        max-width: 500px;
      }
    }
    .bento-grid {
      grid-template-columns: repeat(2, 1fr);
      > :nth-child(1) {
        grid-column: span 2;
      }
    }
    .footer-cta {
      max-width: 600px;
    }
  }
}

@media (min-width: 1280px) {
  #future {
    padding: 50px;
    .heading {
      h2 {
        font-size: 35px;
      }
      p {
        margin: 0 auto;
        max-width: 600px;
      }
    }
    .bento-grid {
      grid-template-columns: repeat(9, 1fr);
      .card {
        padding: 25px;
      }
      > :nth-child(1) {
        grid-column: span 5;
      }
      > :nth-child(2) {
        grid-column: span 4;
      }
      > :nth-child(3) {
        grid-column: span 3;
      }
      > :nth-child(4) {
        grid-column: span 3;
      }
      > :nth-child(5) {
        grid-column: span 3;
      }
    }
    .footer-cta {
      max-width: 800px;
    }
  }
}
</style>