<script setup lang="ts">
import CButton from "@/components/Button.vue";
import Logo from "@/components/Logo.vue";
import Number from "@/components/Number.vue";
import FooterDesktop from "@/assets/desktop/image-footer.jpg";
import FooterTablet from "@/assets/tablet/image-footer.jpg";
import FooterMobile from "@/assets/mobile/image-footer.jpg";
</script>

<template>
  <main class="flow">
    <Logo class="mt-l-4xl mx-auto" />
    <div
      class="gap-4xl mt-l-4xl flex flex-col items-center justify-center overflow-x-hidden xl:flex-row"
    >
      <img
        src="@/assets/desktop/image-hero-left.png"
        alt="Six small profile pictures of people"
        width="394"
        height="303"
        class="-ml-8 hidden xl:block"
      />

      <img
        src="@/assets/tablet/image-hero.png"
        alt="Six small profile pictures of people"
        width="820"
        height="303"
        class="w-[calc(100%+4rem)] max-w-[850px] xl:hidden"
      />

      <article class="flow flex max-w-[40ch] flex-col items-center text-center">
        <h1 class="text-4xl">Group Chat for Everyone</h1>
        <p>
          Meet makes it easy to connect with others face-to-face virtually and
          collaborate across any device.
        </p>
        <div class="gap-s flex flex-wrap justify-center">
          <CButton variant="primary"
            >Download <span class="text-primary-accent">v1.3</span></CButton
          >
          <CButton variant="secondary">What is it?</CButton>
        </div>
      </article>

      <img
        src="@/assets/desktop/image-hero-right.png"
        alt="Six small profile pictures of people"
        width="394"
        height="303"
        class="-mr-8 hidden xl:block"
      />
    </div>

    <Number :value="1" style="--flow-space: var(--spacing-4xl-6xl)" />

    <article
      class="flex flex-col items-center justify-center text-center"
      style="--flow-space: var(--spacing-3xl)"
    >
      <div class="gap-s lg:gap-xs-l flex flex-wrap items-center justify-center">
        <div class="gap-s lg:gap-xs-l flex items-center justify-center">
          <img
            class="w-fluid-144-256 rounded-xs"
            src="@/assets/desktop/image-woman-in-videocall.jpg"
            alt="A woman in a video call"
            width="510"
            height="484"
          />
          <img
            class="w-fluid-144-256 rounded-xs"
            src="@/assets/desktop/image-women-videochatting.jpg"
            alt="Three women video chatting"
            width="510"
            height="484"
          />
        </div>
        <div class="gap-s lg:gap-xs-l flex items-center justify-center">
          <img
            class="w-fluid-144-256 rounded-xs"
            src="@/assets/desktop/image-men-in-meeting.jpg"
            alt="Men in a video meeting"
            width="510"
            height="484"
          />
          <img
            class="w-fluid-144-256 rounded-xs"
            src="@/assets/desktop/image-man-texting.jpg"
            alt="Man texting on a phone"
            width="510"
            height="484"
          />
        </div>
      </div>

      <div class="flow mt-2xl max-w-[45ch]">
        <h2 class="text-primary text-s tracking-xs uppercase">
          Built for modern use
        </h2>
        <h3 class="mt-s leading-xl text-xl">
          Smarter meetings, all in one place
        </h3>
        <p>
          Send messages, share files, show your screen, and record your meetings
          — all in one workspace. Control who can join with invite-only team
          access, data encryption, and data export.
        </p>
      </div>
    </article>

    <Number :value="2" class="translate-y-xl" />

    <div class="overlay-grid">
      <picture>
        <source media="(max-width: 767px)" :srcset="FooterMobile" />
        <source media="(max-width: 1440px)" :srcset="FooterTablet" />
        <img
          :src="FooterDesktop"
          alt="A woman sitting on a couch, joining a video call on her laptop"
          class="max-h-[375px] w-full object-cover object-top"
        />
      </picture>
      <div class="bg-primary/90"></div>
      <article
        class="flow-grid mx-auto place-content-center place-items-center text-center lg:text-left"
        style="--padding: var(--spacing-l-4xl)"
      >
        <h2 class="leading-xl text-xl font-black text-white">
          Experience more together
        </h2>
        <p class="text-white">
          Stay connected with reliable HD meetings and unlimited one-on-one and
          group video sessions.
        </p>
        <CButton variant="secondary"
          >Download <span class="text-secondary-accent">v1.3</span></CButton
        >
      </article>
    </div>
  </main>

  <footer></footer>
</template>

<style scoped>
article {
  --padding: var(--spacing-l);
  padding-inline: var(--padding);
}

.flow-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 2rem;
}

@media (min-width: 1440px) {
  .flow-grid {
    grid-template-columns: 2fr 2fr 1fr;
  }
}

.overlay-grid {
  display: grid;
}

.overlay-grid > * {
  grid-column: 1 / 1;
  grid-row: 1 / 1;
}
</style>
