<script setup lang='ts'>
import gsap from "gsap";
import ScrollTrigger from "gsap/dist/ScrollTrigger";

import projectsPage from "~/content/projects-page.ts";
import { ctaSection } from "~/content/home-page.ts";
import { useEffect } from "~/hooks/core.vue";

useEffect(() => {
	gsap.registerPlugin(ScrollTrigger);

	gsap.fromTo(
		"#text-2",
		{ opacity: 0, yPercent: 25 },
		{
			opacity: 1,
			yPercent: 0,
			scrollTrigger: "#text-2",
		},
	);

	gsap.fromTo(
		"#cta-btn",
		{ opacity: 0 },
		{
			opacity: 1,
			scrollTrigger: "#cta-btn",
		},
	);
});
</script>

<template>
  <section id="cta-section" class="pb-16 px-8 lg:px-16 lg:grid grid-rows-[auto]">
    <div class="grid gap-12 lg:grid-cols-6 place-items-center overflow-hidden">
      <p id="text-2" class="lg:col-span-4 text-lg lg:text-2xl leading-loose lg:leading-loose">
        {{ ctaSection.para }}
      </p>
      <a id="cta-btn" 
        class="lg:col-span-2 p-12 border border-[#fe4164] rounded-full h-64 w-64 flex justify-center items-center uppercase text-sm transition duration-300 hover:bg-[#fe4164] hover:text-white"
				:href="projectsPage.url"
				>
        {{ projectsPage.labelForCTA }}
      </a>
    </div>
  </section>
</template>
