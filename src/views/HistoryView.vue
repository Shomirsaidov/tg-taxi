<template>
    <div class="my-bg min-h-screen p-4">
      <div v-for="(item, index) in locations" :key="index" class="bg-white rounded-lg border-b-2 border-gray-400 mb-4 p-4">
        <div class="flex justify-between items-center mb-2">
          <span class="text-sm text-gray-500">{{ item.date }}, {{ item.time }}</span>
          <div class="flex items-center">
            <span v-for="star in 5" :key="star" class="text-yellow-400 text-lg">
              <!-- <i class="fas" :class="star <= item.rating ? 'fa-star' : 'fa-star-o'"></i> -->
              <img v-if="star > item.rating" src="../assets/star-o.png" alt="">
              <img v-if="star <= item.rating" src="../assets/star.png" alt="">
            </span>
          </div>
        </div>
        <div class="space-y-3 my-4">
          <div class="flex items-center space-x-3">
            <img src="../assets/target.svg" alt="">
            <div class="text-start">{{ item.address }}</div>
          </div>
          <div class="flex items-center space-x-3">
            <img src="../assets/location.svg" alt="">
            <div class="text-start">{{ item.place }}</div>
          </div>
        </div>
        <p class="text-blue-500 text-start text-lg font-semibold mt-2">{{ item.price }} грн</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        locations: [
          {
            date: "01.11.24",
            time: "14:04",
            rating: 5,
            address: "Проспект Добровольского, 111",
            place: "Супермаркет Ашан",
            price: 145,
          },
          {
            date: "12.09.24",
            time: "11:55",
            rating: 5,
            address: "Проспект Добровольского, 111",
            place: "Ресторан Сканди\nПроспект Добровольского, 126",
            price: 157,
          },
          {
            date: "10.07.24",
            time: "21:09",
            rating: 4,
            address: "Проспект Добровольского, 111",
            place: "Ресторан Сканди\nПроспект Добровольского, 126",
            price: 170,
          },
          {
            date: "08.07.24",
            time: "19:20",
            rating: 3,
            address: "Проспект Добровольского, 111",
            place: "Клиника Альт-Мед\nСемена Паля, 78",
            price: 134,
          },
        ],
      };
    },
  };
  </script>
  
  <style>
  body {
    font-family: 'Inter', sans-serif;
  }
  </style>
  