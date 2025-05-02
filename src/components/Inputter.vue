<script setup>
import { ref } from 'vue'
defineProps({
  msg: {
    type: String,
    required: true,
  },
})

const input = ref();

function getTusta(c) {
  let ret = '';
  switch (c) {
    case '0': ret = '数字のゼロ'; break;
    case '1': ret = '数字のイチ'; break;
    case '2': ret = '数字のニ'; break;
    case '3': ret = '数字のサン'; break;
    case '4': ret = '数字のヨン'; break;
    case '5': ret = '数字のゴ'; break;
    case '6': ret = '数字のロク'; break;
    case '7': ret = '数字のナナ'; break;
    case '8': ret = '数字のハチ'; break;
    case '9': ret = '数字のキュウ'; break;

    case 'a': ret = '小文字のエー'; break;
    case 'b': ret = '小文字のビー'; break;
    case 'c': ret = '小文字のシー'; break;
    case 'd': ret = '小文字のデー'; break;
    case 'e': ret = '小文字のイー'; break;
    case 'f': ret = '小文字のエフ'; break;
    case 'g': ret = '小文字のジー'; break;
    case 'h': ret = '小文字のエイチ'; break;
    case 'i': ret = '小文字のアイ'; break;
    case 'j': ret = '小文字のジェイ'; break;
    case 'k': ret = '小文字のケー'; break;
    case 'l': ret = '小文字のエル'; break;
    case 'm': ret = '小文字のエム'; break;
    case 'n': ret = '小文字のエヌ'; break;
    case 'o': ret = '小文字のオー'; break;
    case 'p': ret = '小文字のピー'; break;
    case 'q': ret = '小文字のキュー'; break;
    case 'r': ret = '小文字のアール'; break;
    case 's': ret = '小文字のエス'; break;
    case 't': ret = '小文字のテー'; break;
    case 'u': ret = '小文字のユー'; break;
    case 'v': ret = '小文字のブイ'; break;
    case 'w': ret = '小文字のダブリュー'; break;
    case 'x': ret = '小文字のエックス'; break;
    case 'y': ret = '小文字のワイ'; break;
    case 'z': ret = '小文字のゼット'; break;

    case 'A': ret = '大文字のエー'; break;
    case 'B': ret = '大文字のビー'; break;
    case 'C': ret = '大文字のシー'; break;
    case 'D': ret = '大文字のデー'; break;
    case 'E': ret = '大文字のイー'; break;
    case 'F': ret = '大文字のエフ'; break;
    case 'G': ret = '大文字のジー'; break;
    case 'H': ret = '大文字のエイチ'; break;
    case 'I': ret = '大文字のアイ'; break;
    case 'J': ret = '大文字のジェイ'; break;
    case 'K': ret = '大文字のケー'; break;
    case 'L': ret = '大文字のエル'; break;
    case 'M': ret = '大文字のエム'; break;
    case 'N': ret = '大文字のエヌ'; break;
    case 'O': ret = '大文字のオー'; break;
    case 'P': ret = '大文字のピー'; break;
    case 'Q': ret = '大文字のキュー'; break;
    case 'R': ret = '大文字のアール'; break;
    case 'S': ret = '大文字のエス'; break;
    case 'T': ret = '大文字のテー'; break;
    case 'U': ret = '大文字のユー'; break;
    case 'V': ret = '大文字のブイ'; break;
    case 'W': ret = '大文字のダブリュー'; break;
    case 'X': ret = '大文字のエックス'; break;
    case 'Y': ret = '大文字のワイ'; break;
    case 'Z': ret = '大文字のゼット'; break;

  }

  return ret;
}
</script>

<template>
  <div>
    <input v-model="input" />
  </div>

  <div>
    <ul>
      <li v-for="c in input">
        {{ c }} : {{ getTusta(c) }}
      </li>
    </ul>
  </div>
</template>

<style scoped></style>
