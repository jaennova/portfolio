<script>
  import { onMount } from "svelte";
  import Icon from "@iconify/svelte";
  import personalData from "../data/personal.json";

  let visible = false;

  onMount(() => {
    visible = true;
  });
</script>

<section
  id="home"
  class="min-h-screen flex items-center justify-center pt-20 md:pt-0"
>
  <div class="max-w-6xl mx-auto px-4">
    <div
      class="flex flex-col lg:flex-row items-center gap-12 {visible
        ? 'opacity-100'
        : 'opacity-0'} transition-opacity duration-1000"
    >
      <div class="lg:w-1/3 relative group">
        <div
          class="absolute -inset-0.5 bg-gradient-to-r from-android-light to-python-light rounded-full blur opacity-30 group-hover:opacity-50 transition duration-1000"
        ></div>
        <div class="relative aspect-square w-64 mx-auto">
          <img
            src={personalData.profile.image}
            alt={personalData.name}
            class="w-full h-full object-cover rounded-full border-4 border-android-light dark:border-python-light shadow-xl"
          />
        </div>
      </div>

      <div class="lg:w-2/3 text-center lg:text-left">
        <h1
          class="text-4xl lg:text-6xl font-bold mb-4 bg-gradient-to-r from-android-light to-python-light bg-clip-text text-transparent"
        >
          {personalData.name}
        </h1>

        <p class="text-xl lg:text-2xl text-gray-600 dark:text-gray-400 mb-8">
          {personalData.role}
        </p>

        <div class="flex flex-wrap justify-center lg:justify-start gap-4 mb-8">
          <a
            href={personalData.contact.email.link}
            class="flex items-center gap-2 px-6 py-3 rounded-lg bg-gradient-to-r from-android-light to-android-dark dark:from-python-light dark:to-python-dark text-white hover:opacity-90 transition-all duration-300 hover:scale-105"
          >
            <Icon icon="carbon:email" class="w-5 h-5" />
            {personalData.contact.email.value}
          </a>
        </div>

        <div class="flex justify-center lg:justify-start gap-4">
          <a
            href={personalData.contact.github.link}
            target="_blank"
            rel="noopener noreferrer"
            class="flex items-center gap-2 px-6 py-3 rounded-lg bg-gray-900 dark:bg-white text-white dark:text-gray-900 hover:opacity-90 transition-all duration-300 hover:scale-105"
          >
            <Icon icon="simple-icons:github" class="w-5 h-5" />
            {personalData.contact.github.title}
          </a>
          <a
            href={personalData.contact.linkedin.link}
            target="_blank"
            rel="noopener noreferrer"
            class="flex items-center gap-2 px-6 py-3 rounded-lg bg-[#0A66C2] text-white hover:opacity-90 transition-all duration-300 hover:scale-105"
          >
            <Icon icon="simple-icons:linkedin" class="w-5 h-5" />
            {personalData.contact.linkedin.title}
          </a>
        </div>
      </div>
    </div>
  </div>
</section>
