<template>
  <div class="flex flex-col m-[5%] gap-y-10 justify-center items-center">
    <div class="flex md:flex-row flex-col flex-warp items-center justify-center gap-y-10 w-full">
      <img class="flex size-[50%] md:size-[25%] rounded-full outline-2 outline-offset-4 outline-[#cba6f7]/25"
        :src="userdata.avatar.path" />
      <div class="flex flex-col gap-y-5 items-center">
        <h1 class="font-bold text-5xl">{{ userdata.username }}</h1>

        <hr class="flex border border-[#cba6f7]/25 size-auto w-[75%]" />

        <div class="flex flex-row self-center items-center justify-center" v-for="(i, social) in userdata.socials">
          <a class="flex self-center items-center justify-center" :href="i">
            <span
              class="flex items-center justify-center size-[10%] rounded-full hover:outline-2 outline-offset-4 outline-[#f38ba8]/50">
              <img class="invert" :src="social" :href="i" />
            </span>
          </a>
        </div>
      </div>
    </div>
    <hr class="flex border border-[#cba6f7]/25 size-auto w-[75%]" />
    <div class="flex items-start justify-start w-[75%]">
      <p class="text-xl text-start">
        {{ userdata.about }}
      </p>
    </div>
    <hr class="flex border border-[#cba6f7]/25 size-auto w-[75%]" />
    <div class="flex flex-col gap-y-5 w-[50%]">
      <h2 class="font-bold text-4xl mx-auto">Friends</h2>
      <div class="flex flex-col" v-for="friend in friends">
        <div class="flex items-center gap-5 rounded-full outline outline-offset-4 outline-[#f38ba8]/50">
          <img class="size-[15%] rounded-full" :src="friend.avatar" />
          <div class="my-max text-center">
            <p class="font-bold text-start text-2xl">
              {{ friend.display_name ? friend.display_name : friend.name }}
            </p>
            <p class="text-[#7f849c] font-light text-2xl" v-if="friend.display_name">
              {{ friend.name }}
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
const userdata = {
  username: "Deppie",
  avatar: {
    path: "avatar.png",
  },
  socials: { "github.png": "https://github.com/Depreca1ed" },
  about: "I love thighs.",
};

const friends = [
  {
    name: "itswilliboy",
    display_name: "Willi",
    redirect: "https://itswilli.dev/",
    avatar: "https://itswilli.dev/_vercel/image?url=%2Fmilo.jpg&w=1536&q=100",
  },
  {
    name: "du_cki",
    display_name: null,
    redirect: "https://faaz.dev/",
    avatar: "https://avatars.githubusercontent.com/u/70286349",
  },
];
</script>

<style></style>
