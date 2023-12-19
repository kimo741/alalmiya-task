<template>
  <div class="container h-[463px] bg-[#004837]">
    <div class="flex flex-col justify-center items-center w-full h-full">
      <div class="flex justify-center items-center mb-5">
        <div
          class="w-[64px] h-[82px] text-[56px] font-bold bg-[#FF4300] text-white text-center mr-1 rounded-[4px]"
        >
          {{ firstDigitHour }}
        </div>
        <div
          class="w-[64px] h-[82px] text-[56px] font-bold bg-[#FF4300] text-white text-center mr-3 rounded-[4px]"
        >
          {{ socDigitHour }}
        </div>
        <span class="text-white text-[20px] font-bold">:</span>
        <div
          class="w-[64px] h-[82px] text-[56px] font-bold bg-[#FF4300] text-white text-center ml-3 mr-1 rounded-[4px]"
        >
          {{ firstDigitMinute }}
        </div>
        <div>
          <div
            class="w-[64px] h-[82px] text-[56px] font-bold bg-[#FF4300] text-white text-center mr-1 rounded-[4px]"
          >
            {{ socDigitMinute }}
          </div>
        </div>
      </div>
      <div class="text-[40px] text-[#FF4300] font-bold text-center">
        -40% on all Personal Care products
      </div>
      <div class="text-[14px] text-white text-center w-[50%]">
        *Some explanation small text if needed displayed here. Lorem ipsum dolor
        sit amet, consectetur adipiscing elit. Donec lobortis egestas mi
      </div>
      <div class="w-full flex justify-center items-center">
        <button
          type="button"
          class="my-3 bg-[#FF4300] text-white hover:bg-[#ff440073] focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 me-2 mb-2 dark:bg-blue-600 dark:hover:bg-blue-700"
        >
          Shop Now
        </button>
      </div>
    </div>
    <!-- <h1>{{ hours }} : {{ minutes }} : {{ seconds }}</h1> -->
  </div>
</template>
  
  <script setup>
//   state
const firstDigitHour = ref("3");
const socDigitHour = ref("2");
const firstDigitMinute = ref("5");
const socDigitMinute = ref("9");
const hours = ref(32);
const minutes = ref(59);
const seconds = ref(0);
const timer = ref(null);
// methods
const getDigitH = (number) => {
  const numberStr = number.toString();
  firstDigitHour.value = parseInt(numberStr.charAt(0));
  socDigitHour.value = parseInt(numberStr.charAt(1));
};
const getDigitM = (number) => {
  const numberStr = number.toString();
  firstDigitMinute.value = parseInt(numberStr.charAt(0));
  socDigitMinute.value = parseInt(numberStr.charAt(1));
};
const startTimer = () => {
  timer.value = setInterval(() => {
    if (seconds.value > 0) {
      seconds.value--;
    } else {
      if (minutes.value > 0) {
        minutes.value--;
        seconds.value = 59;
      } else {
        if (hours.value > 0) {
          hours.value--;
          minutes.value = 59;
          seconds.value = 59;
        } else {
          clearInterval(timer.value);
        }
      }
    }
  }, 1000);
};
// watchers
watch(hours, (newVal) => {
  getDigitH(newVal);
});
watch(minutes, (newVal) => {
  getDigitM(newVal);
});
// hook
onMounted(() => {
  getDigitH(hours.value);
  getDigitM(minutes.value);
  startTimer();
});
</script>