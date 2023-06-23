<template>
  <div
    class="relative bg-white border border-gray-200 rounded-t-lg shadow"
    :style="{ width: width }"
  >
    <div class="relative flex items-start overflow-hidden rounded">
      <img
        class="object-contain"
        :src="`/_nuxt/assets/image/card/${gameImage}`"
        :alt="titleHeading"
        :style="{ height: height }"
      />
    </div>
    <div
      v-if="isNew"
      class="absolute top-2 -left-1 w-16 inline-flex items-center"
    >
      <svg
        width="39"
        height="39"
        viewBox="0 0 39 22"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M0 3C0 1.34315 1.34315 0 3 0H36C37.6569 0 39 1.34315 39 3V15C39 16.6569 37.6569 18 36 18H0V3Z"
          fill="#EE7326"
        />
        <path
          d="M16.6387 13H15.5467L11.1547 6.34V13H10.0627V4.624H11.1547L15.5467 11.272V4.624H16.6387V13ZM24.5002 9.46C24.5002 9.668 24.4882 9.888 24.4642 10.12H19.2082C19.2482 10.768 19.4682 11.276 19.8682 11.644C20.2762 12.004 20.7682 12.184 21.3442 12.184C21.8162 12.184 22.2082 12.076 22.5202 11.86C22.8402 11.636 23.0642 11.34 23.1922 10.972H24.3682C24.1922 11.604 23.8402 12.12 23.3122 12.52C22.7842 12.912 22.1282 13.108 21.3442 13.108C20.7202 13.108 20.1602 12.968 19.6642 12.688C19.1762 12.408 18.7922 12.012 18.5122 11.5C18.2322 10.98 18.0922 10.38 18.0922 9.7C18.0922 9.02 18.2282 8.424 18.5002 7.912C18.7722 7.4 19.1522 7.008 19.6402 6.736C20.1362 6.456 20.7042 6.316 21.3442 6.316C21.9682 6.316 22.5202 6.452 23.0002 6.724C23.4802 6.996 23.8482 7.372 24.1042 7.852C24.3682 8.324 24.5002 8.86 24.5002 9.46ZM23.3722 9.232C23.3722 8.816 23.2802 8.46 23.0962 8.164C22.9122 7.86 22.6602 7.632 22.3402 7.48C22.0282 7.32 21.6802 7.24 21.2962 7.24C20.7442 7.24 20.2722 7.416 19.8802 7.768C19.4962 8.12 19.2762 8.608 19.2202 9.232H23.3722ZM34.7016 6.424L32.6496 13H31.5216L29.9376 7.78L28.3536 13H27.2256L25.1616 6.424H26.2776L27.7896 11.944L29.4216 6.424H30.5376L32.1336 11.956L33.6216 6.424H34.7016Z"
          fill="white"
        />
        <path d="M5 18H0L5 21.5V18Z" fill="#C85710" />
      </svg>
    </div>
    <div class="p-5">
      <div class="flex items-start space-x-4">
        <div>
          <div class="font-semibold overflow-hidden truncate w-72">
            {{ titleHeading }}
          </div>
          <div class="mt-2">
            <div class="text-sm text-gray-500 font-normal">
              {{ viewer }}
            </div>
          </div>
          <div class="flex space-x-4 mt-2">
            <div v-for="game in gameCategory" :key="game">
              <ButtonBasicComponent :text="game" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import ButtonBasicComponent from '../Buttons/ButtonBasicComponent.vue';
defineProps<{
  titleHeading: string;
  gameImage: string;
  gameCategory?: string[];
  viewer?: string | number;
  height: string | number;
  width: string | number;
  isNew?: boolean;
}>();
</script>
<style scoped>
.live-badge {
  background-color: #f35625;
}
.viewer-badge {
  background-color: rgba(35, 31, 32, 0.8);
}
</style>
