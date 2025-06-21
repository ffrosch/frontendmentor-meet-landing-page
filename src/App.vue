<script setup lang="ts">
import CButton from '@/components/Button.vue';
import Logo from '@/components/Logo.vue';
import Number from '@/components/Number.vue';
</script>

<template>
  <div>
    <Logo />
    <h1>Group Chat for Everyone</h1>
    <p>Meet makes it easy to connect with others face-to-face virtually and collaborate across any device.</p>
    <CButton variant="primary">Download <span class="text-primary-light">v1.3</span></CButton>
    <CButton variant="secondary">What is it?</CButton>

    <Number :value="1" />

    <h2>Built for modern use</h2>

    <h3>Smarter meetings, all in one place</h3>

    <p>Send messages, share files, show your screen, and record your meetings — all in one
      workspace. Control who can join with invite-only team access, data encryption, and data export.</p>

    <Number :value="2" />

    <section class="flex items-center bg-primary text-white">
      <p class="text-xl font-black">Experience more together</p>
      <p>Stay connected with reliable HD meetings and unlimited one-on-one and group video sessions.</p>
      <CButton variant="secondary">Download <span class="text-secondary-light">v1.3</span></CButton>
    </section>
  </div>
</template>

<style scoped></style>