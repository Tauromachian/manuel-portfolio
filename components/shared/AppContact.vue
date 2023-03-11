<script>
import feather from "feather-icons";
import ContactForm from "../contact/ContactForm.vue";
export default {
  components: { ContactForm },
  data: () => {
    return {
      socialProfiles: [
        {
          name: "Youtube",
          route: "/assets/youtube 1.png",
          url: "https://youtube.com/",
        },
        {
          name: "Spotify",
          route: "/assets/spotify 1.png",
          url: "https://spotify.com/",
        },
        {
          name: "Facebook",
          route: "/assets/facebook 1.png",
          url: "https://facebook.com/",
        },
        {
          name: "Twitter",
          route: "/assets/twitter 1.png",
          url: "https://twitter.com/",
        },
        {
          name: "ITunes",
          route: "/assets/apple 1.png",
          url: "https://itunes.com/",
        },
      ],
    };
  },

  mounted() {
    feather.replace();
  },
  updated() {
    feather.replace();
  },
};
</script>

<template>
  <div class="container mx-auto">
    <div class="pt-20 sm:pt-30 pb-8 mt-20 border-t-2 border-secondary-dark">
      <!-- Footer social links -->
      <div
        class="flex w-full flex-col justify-center items-center mb-12 sm:mb-20"
      >
        <p
          class="
            font-general-semibold
            text-6xl text-primary-light
            mb-5
            textTitle
          "
        >
          Follow me
        </p>

        <!-- Contact section -->

        <div
          class="
            flex flex-col
            mr-0
            md:mr-16 md:flex-row
            w-full
            justify-center
            items-center
          "
        >
          <ul class="flex flex-row md:flex-col gap-4 z-10 sm:gap-8">
            <a
              v-for="(social, id) in socialProfiles"
              :key="id"
              :href="social.url"
              target="__blank"
              class="cursor-pointer shadow-sm duration-500"
            >
              <img :src="social.route" :alt="social.name" />
            </a>
          </ul>
          <ContactForm />
        </div>
        <!-- Contact section -->
      </div>
    </div>
  </div>
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Cookie&family=PT+Sans+Caption&display=swap");

.textTitle {
  font-family: "Cookie", cursive;
}
</style>
