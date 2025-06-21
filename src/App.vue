<script setup lang="ts">
import CButton from '@/components/Button.vue';
import Logo from '@/components/Logo.vue';
import Number from '@/components/Number.vue';
import FooterDesktop from "@/assets/desktop/image-footer.jpg";
import FooterTablet from "@/assets/tablet/image-footer.jpg";
import FooterMobile from "@/assets/mobile/image-footer.jpg";
</script>

<template>
  <main>
    <Logo class="mx-auto" />
    <div class="flex justify-between items-center">
      <img
        src="@/assets/desktop/image-hero-left.png"
        alt="Six small profile pictures of people"
        width="394"
        height="303"
      >

      <section class="flex flex-col items-center text-center max-w-[40ch]">
        <h1 class="text-4xl">Group Chat for Everyone</h1>
        <p>Meet makes it easy to connect with others face-to-face virtually and collaborate across any device.</p>
        <div class="flex flex-wrap gap-s justify-center">
          <CButton variant="primary">Download <span class="text-primary-light">v1.3</span></CButton>
          <CButton variant="secondary">What is it?</CButton>
        </div>
      </section>

      <img
        src="@/assets/desktop/image-hero-right.png"
        alt="Six small profile pictures of people"
        width="394"
        height="303"
      >
    </div>

    <Number :value="1" />

    <article class="flex flex-col justify-center items-center">
      <div class="flex flex-wrap gap-l justify-center items-center">
        <div class="flex gap-l justify-center items-center">
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
        <div class="flex gap-l justify-center items-center">
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

      <h2 class="text-primary text-s tracking-xs uppercase">Built for modern use</h2>
      <h3 class="text-xl">Smarter meetings, all in one place</h3>
      <p>Send messages, share files, show your screen, and record your meetings — all in one
        workspace. Control who can join with invite-only team access, data encryption, and data export.</p>
    </article>

    <Number :value="2" />

    <div class="overlay-grid">
      <picture>
        <source
          media="(max-width: 767px)"
          :srcset="FooterMobile"
        />
        <source
          media="(max-width: 1023px)"
          :srcset="FooterTablet"
        />
        <img
          :src="FooterDesktop"
          alt="A woman sitting on a couch, joining a video call on her laptop"
          class="w-full max-h-[375px] object-cover object-top"
        />
      </picture>

      <article class="flex justify-center items-center bg-primary/90 [&_*]:text-white">
        <h2 class="text-xl font-black">Experience more together</h2>
        <p>Stay connected with reliable HD meetings and unlimited one-on-one and group video sessions.</p>
        <CButton variant="secondary">Download <span class="text-secondary-light">v1.3</span></CButton>
      </article>
    </div>
  </main>

  <footer></footer>
</template>

<style scoped>
.overlay-grid {
  display: grid;
}

.overlay-grid > * {
  grid-column: 1 / 1;
  grid-row: 1 / 1;
}
</style>