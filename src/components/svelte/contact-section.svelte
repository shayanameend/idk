<script lang="ts">
import gsap from "gsap";

import { socialLinks } from "~/content/common.ts";
import { contactSection } from "~/content/contact-page.ts";
import { useEffect } from "~/hooks/core.svelte";

useEffect(() => {
	gsap.to(["#contact-heading", "#contact-info", "#contact-paragraph"], {
		duration: 0.35,
		stagger: 0.15,
		opacity: 1,
		y: 0,
	});
});
</script>

<section class="overflow-hidden">
  <div class="p-2 lg:p-16">
    <h3
      id="contact-heading"
      class="opacity-0 translate-y-full px-2 lg:px-0 py-8 text-7xl md:text-[8rem]"
    >
      <span>
        Contact
      </span>
      <span class="font-bold text-[#fe4164]">
        .
      </span>
    </h3>
    <div
      id="contact-info"
      class="opacity-0 translate-y-full px-4 mb-12 flex flex-col lg:flex-row gap-12 lg:gap-24"
    >
      <div class="flex-1 space-y-4">
        <form class="mt-10" name="contact" method="POST" data-netlify="true">
          <div class="grid gap-6 sm:grid-cols-2">
            <div class="relative z-0">
              <input type="text" id="name" name="name" class="peer block w-full appearance-none border-0 border-b border-[#fe4164] bg-transparent py-2.5 px-0 text-sm text-gray-900 focus:border-[#fe4164] focus:outline-none focus:ring-0" placeholder=" " />
              <label for="name" class="absolute top-3 -z-10 origin-[0] -translate-y-6 scale-75 transform text-sm text-gray-500 duration-300 peer-placeholder-shown:translate-y-0 peer-placeholder-shown:scale-100 peer-focus:left-0 peer-focus:-translate-y-6 peer-focus:scale-75 peer-focus:text-[#fe4164] peer-focus:dark:text-[#fe4164]">Your name</label>
            </div>
            <div class="relative z-0">
              <input type="text" id="email" name="email" class="peer block w-full appearance-none border-0 border-b border-[#fe4164] bg-transparent py-2.5 px-0 text-sm text-gray-900 focus:border-[#fe4164] focus:outline-none focus:ring-0" placeholder=" " />
              <label for="email" class="absolute top-3 -z-10 origin-[0] -translate-y-6 scale-75 transform text-sm text-gray-500 duration-300 peer-placeholder-shown:translate-y-0 peer-placeholder-shown:scale-100 peer-focus:left-0 peer-focus:-translate-y-6 peer-focus:scale-75 peer-focus:text-[#fe4164] peer-focus:dark:text-[#fe4164]">Your email</label>
            </div>
            <div class="relative z-0 col-span-2">
              <textarea id="message" name="message" rows="5" class="peer block w-full appearance-none border-0 border-b border-[#fe4164] bg-transparent py-2.5 px-0 text-sm text-gray-900 focus:border-[#fe4164] focus:outline-none focus:ring-0" placeholder=" "></textarea>
              <label for="message" class="absolute top-3 -z-10 origin-[0] -translate-y-6 scale-75 transform text-sm text-gray-500 duration-300 peer-placeholder-shown:translate-y-0 peer-placeholder-shown:scale-100 peer-focus:left-0 peer-focus:-translate-y-6 peer-focus:scale-75 peer-focus:text-[#fe4164] peer-focus:dark:text-[#fe4164]">Your message</label>
            </div>
          </div>
          <button type="submit" class="mt-5 border border-[#fe4164] rounded-md px-10 py-2 transition duration-300 hover:bg-[#fe4164] hover:text-white">Send Message</button>
        </form>
      </div>
      <div class="flex-1 space-y-8 text-lg md:text-2xl">
        <div>
          <h4>{contactSection.address.line1}</h4>
          <h4>{contactSection.address.line2}</h4>
          <p>
            <span> T: </span>
            <span>{contactSection.telephoneNumber}</span>
          </p>
          <p>
            <span> E: </span>
            <span>{contactSection.emailAddress}</span>
          </p>
        </div>
        <div>
          <!-- <h4>{contactSection.address.country}</h4> -->
          <ul class="-ml-1 flex gap-4 items-center">
            {#each socialLinks as {url, SvelteIcon}}
              <li>
                <a href={url}>
                  <SvelteIcon />
                </a>
              </li>
            {/each}
          </ul>
        </div>
      </div>
    </div>
    <p
      id="contact-paragraph"
      class="opacity-0 translate-y-full px-4 py-8 text-lg lg:text-2xl leading-loose lg:leading-loose"
      >
      {contactSection.para}
    </p>
  </div>
</section>
