<script lang="ts">
import gsap from "gsap";

import Project from "~/components/svelte/project.svelte";
import { projectsSection } from "~/content/projects-page.ts";
import { useEffect } from "~/hooks/core.svelte";

useEffect(() => {
	gsap.to(["#projects-heading", "#projects-paragraph"], {
		duration: 0.35,
		stagger: 0.15,
		opacity: 1,
		y: 0,
	});
});
</script>

<section class="min-h-[calc(100vh_-_69px)] lg:min-h-screen overflow-hidden">
  <div class="p-2 lg:p-16">
    <h3
      id="projects-heading"
      class="opacity-0 translate-y-1/4 px-2 lg:px-0 py-8 text-7xl md:text-[8rem]"
    >
      <span>
        Our Projects
      </span>
      <span class="font-bold text-[#fe4164]">
        .
      </span>
    </h3>
    <p
      id="projects-paragraph"
      class="opacity-0 translate-y-1/4 px-4 pb-12 text-lg lg:text-2xl leading-loose lg:leading-loose"
    >
      {projectsSection.para}
    </p>
    <div class="px-4 grid grid-cols-1 md:grid-cols-2 gap-4 place-items-center">
      {#each projectsSection.projects as item}
        <Project {item} />
      {/each}
    </div>
  </div>
</section>
