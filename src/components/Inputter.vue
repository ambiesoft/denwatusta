<script setup>
import { ref } from 'vue'
defineProps({
  msg: {
    type: String,
    required: true,
  },
})

const input = ref();

function getPron(c) {
  let ret;
  switch (c.toLowerCase()) {
    case '0': ret='ゼロ';  ;break;
    case '1': ret='イチ';  ;break;
    case '2': ret='ニ';    ;break;
    case '3': ret='サン';  ;break;
    case '4': ret='ヨン';  ;break;
    case '5': ret='ゴ';    ;break;
    case '6': ret='ロク';  ;break;
    case '7': ret='ナナ';  ;break;
    case '8': ret='ハチ';  ;break;
    case '9': ret='キュウ' ;break;

    case 'a': ret = 'エー'; break;
    case 'b': ret = 'ビー'; break;
    case 'c': ret = 'シー'; break;
    case 'd': ret = 'デー'; break;
    case 'e': ret = 'イー'; break;
    case 'f': ret = 'エフ'; break;
    case 'g': ret = 'ジー'; break;
    case 'h': ret = 'エイチ'; break;
    case 'i': ret = 'アイ'; break;
    case 'j': ret = 'ジェイ'; break;
    case 'k': ret = 'ケー'; break;
    case 'l': ret = 'エル'; break;
    case 'm': ret = 'エム'; break;
    case 'n': ret = 'エヌ'; break;
    case 'o': ret = 'オー'; break;
    case 'p': ret = 'ピー'; break;
    case 'q': ret = 'キュー'; break;
    case 'r': ret = 'アール'; break;
    case 's': ret = 'エス'; break;
    case 't': ret = 'テー'; break;
    case 'u': ret = 'ユー'; break;
    case 'v': ret = 'ブイ'; break;
    case 'w': ret = 'ダブリュー'; break;
    case 'x': ret = 'エックス'; break;
    case 'y': ret = 'ワイ'; break;
    case 'z': ret = 'ゼット'; break;

    case ' ': ret='スペース'; break;
    case '!': ret='感嘆符、エクスクラメーションマーク、ビックリマーク'; break;
    case '"': ret='引用符、クォーテーションマーク'; break;
    case '#': ret='ナンバーサイン、シャープ'; break;
    case '$': ret='ダラーサイン、ドル'; break;
    case '%': ret='パーセント'; break;
    case '&': ret='アンパサンド'; break;
    case '\'': ret='アポストロフィ'; break;
    case '(': ret='左カッコ'; break;
    case ')': ret='右カッコ'; break;
    case '*': ret='アスタリスク'; break;
    case '+': ret='プラス'; break;
    case ',': ret='カンマ'; break;
    case '-': ret='ハイフン、マイナス'; break;
    case '.': ret='ドット、ピリオド'; break;
    case '/': ret='スラッシュ'; break;
    case ':': ret='コロン'; break;
    case ';': ret='セミコロン'; break;
    case '<': ret='小なり記号'; break;
    case '=': ret='イコール'; break;
    case '>': ret='大なり記号'; break;
    case '?': ret='はてな、クエスチョンマーク'; break;
    case '@': ret='アットマーク'; break;
    case '[': ret='左カギカッコ'; break;
    case '\\': ret='バックスラッシュ'; break;
    case ']': ret='右カギカッコ'; break;
    case '^': ret='ハット'; break;
    case '_': ret='アンダースコア'; break;
    case '`': ret='バッククオート、バックチック'; break;
    case '{': ret='左中カッコ'; break;
    case '|': ret='バーティカルバー'; break;
    case '}': ret='右中カッコ'; break;
    case '~': ret='チルダ、にょろ'; break;    
  }
  return ret;
}
function getTusta2(c) {
  let ret = {
    pron: getPron(c),
    isNumber: false,
    isAlpha: false,
    isCapital: false,
  };
  
  if(Number.isInteger(Number(c))) {
    ret.isNumber=true;
  } else if( /^[a-z]*$/.test(c) ) {
    ret.isAlpha=true;
    ret.isCapital=false;
  } else if( /^[A-Z]*$/.test(c) ) {
    ret.isAlpha=true;
    ret.isCapital=true;
  }
  return ret;
}
function getTusta(c) {
  let ret = getTusta2(c);
  let str = '';
  if(ret.isNumber) {
    str += '数字の';
  } else if(ret.isAlpha) {
    if(ret.isCapital) {
      str += '大文字の';
    } else {
      str += '小文字の';
    }
  } 
  str += ret.pron;
  return str;
}
</script>

<template>
  <div class="inputter">
  <div>
    <input v-model="input" />
  </div>

  <div class="output">
    <ul>
      <li v-for="c in input">
        {{ c }} : {{ getTusta(c) }}
      </li>
    </ul>
  </div>
  </div>
</template>

<style scoped>
.inputter {
  font-family:'Courier New', Courier, monospace;
}
.output {
  padding-top: 20px;
}
li {
  list-style: none;
}
</style>





