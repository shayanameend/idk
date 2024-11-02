<script setup lang='ts'>
import gsap from "gsap";
import ScrollTrigger from "gsap/dist/ScrollTrigger";

import projectsPage from "~/content/projects-page.ts";
import { ctaSection } from "~/content/home-page.ts";
import { useEffect } from "~/hooks/core.vue";

useEffect(() => {
	gsap.registerPlugin(ScrollTrigger);

	gsap.fromTo(
		"#text-1",
		{ opacity: 0, yPercent: 25 },
		{
			opacity: 1,
			yPercent: 0,
			scrollTrigger: "#text-1",
		},
	);
});
</script>

<template>
  <section id="cta-section" class="py-16 px-8 lg:px-16">
    <div class="grid place-items-center overflow-hidden">
      <h2 id="text-1" class="text-3xl lg:text-5xl leading-loose lg:leading-loose">
        {{ ctaSection.quote }}
      </h2>
		</div>
  </section>
</template>
