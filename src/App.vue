<script setup lang="ts">
import CButton from '@/components/Button.vue';
import Logo from '@/components/Logo.vue';
import Number from '@/components/Number.vue';
import FooterDesktop from "@/assets/desktop/image-footer.jpg";
import FooterTablet from "@/assets/tablet/image-footer.jpg";
import FooterMobile from "@/assets/mobile/image-footer.jpg";
</script>

<template>
  <main class="flow">
    <Logo class="mx-auto mt-l-4xl" />
    <div class="flex flex-col xl:flex-row gap-4xl justify-center items-center mt-l-4xl overflow-x-hidden">
      <img
        src="@/assets/desktop/image-hero-left.png"
        alt="Six small profile pictures of people"
        width="394"
        height="303"
        class="hidden xl:block -ml-8"
      >

      <img
        src="@/assets/tablet/image-hero.png"
        alt="Six small profile pictures of people"
        width="820"
        height="303"
        class="xl:hidden w-[calc(100%+4rem)] max-w-[850px]"
      >

      <section class="flow flex flex-col items-center text-center max-w-[40ch]">
        <h1 class="text-4xl">Group Chat for Everyone</h1>
        <p>Meet makes it easy to connect with others face-to-face virtually and collaborate across any device.</p>
        <div class="flex flex-wrap gap-s justify-center">
          <CButton variant="primary">Download <span class="text-primary-accent">v1.3</span></CButton>
          <CButton variant="secondary">What is it?</CButton>
        </div>
      </section>

      <img
        src="@/assets/desktop/image-hero-right.png"
        alt="Six small profile pictures of people"
        width="394"
        height="303"
        class="hidden xl:block -mr-8"
      >
    </div>

    <Number
      :value="1"
      class="mt-4xl lg:mt-6xl"
    />

    <article class="flex flex-col justify-center items-center text-center">
      <div class="flex flex-wrap gap-s lg:gap-xs-l justify-center items-center">
        <div class="flex gap-s lg:gap-xs-l justify-center items-center">
          <img
            class="rounded-xs w-fluid-144-256"
            src="@/assets/desktop/image-woman-in-videocall.jpg"
            alt="A woman in a video call"
            width="510"
            height="484"
          >
          <img
            class="rounded-xs w-fluid-144-256"
            src="@/assets/desktop/image-women-videochatting.jpg"
            alt="Three women video chatting"
            width="510"
            height="484"
          >
        </div>
        <div class="flex gap-s lg:gap-xs-l justify-center items-center">
          <img
            class="rounded-xs w-fluid-144-256"
            src="@/assets/desktop/image-men-in-meeting.jpg"
            alt="Men in a video meeting"
            width="510"
            height="484"
          >
          <img
            class="rounded-xs w-fluid-144-256"
            src="@/assets/desktop/image-man-texting.jpg"
            alt="Man texting on a phone"
            width="510"
            height="484"
          >
        </div>
      </div>

      <div class="flow mt-xl max-w-[45ch]">
        <h2 class="text-primary text-s tracking-xs uppercase">Built for modern use</h2>
        <h3 class="mt-s text-xl leading-xl">Smarter meetings, all in one place</h3>
        <p>Send messages, share files, show your screen, and record your meetings — all in one
          workspace. Control who can join with invite-only team access, data encryption, and data export.</p>
      </div>
    </article>

    <Number
      :value="2"
      class="translate-y-xl"
    />

    <div class="overlay-grid">
      <picture>
        <source
          media="(max-width: 767px)"
          :srcset="FooterMobile"
        />
        <source
          media="(max-width: 1440px)"
          :srcset="FooterTablet"
        />
        <img
          :src="FooterDesktop"
          alt="A woman sitting on a couch, joining a video call on her laptop"
          class="w-full max-h-[375px] object-cover object-top"
        />
      </picture>
      <div class="bg-primary/90"></div>
      <article class="flow-grid place-items-center place-content-center mx-auto text-center lg:text-left px-m md:px-6xl">
        <h2 class="text-white text-xl leading-xl font-black">Experience more together</h2>
        <p class="text-white">Stay connected with reliable HD meetings and unlimited one-on-one and group video sessions.</p>
        <CButton variant="secondary">Download <span class="text-secondary-accent">v1.3</span></CButton>
      </article>
    </div>
  </main>

  <footer></footer>
</template>

<style scoped>
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

.overlay-grid>* {
  grid-column: 1 / 1;
  grid-row: 1 / 1;
}
</style>