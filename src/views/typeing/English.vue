<!--
 * @Author       : hegaohong
 * @Date         : 2023-08-19 17:29:44
 * @LastEditors  : zhanglu
 * @LastEditTime : 2023-08-20 09:22:26
 * @company      : 沐秦智能
 * @FilePath     : \repidtyping\src\views\typeing\English.vue
 * @Descripttion : 
-->
<template>
  <h3 class="title">
    {{ `《${content?.title}》${content?.author}` }}
  </h3>
  <div class="content" id="content">
    <div v-for="item in content?.content" :key="item" class="content-item">
      <div class="pinyin">
        <span v-for="char in item" :key="char" class="py-item">
          {{ char }}
        </span>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.title {
  color: rgb(255, 255, 255);
}
.content {
  max-width: 10rem;
  max-height: 4.5rem;
  font-size: 0.28rem;
  margin: 0 auto;
  padding: 0.12rem 0;
  overflow-y: scroll;
  transition: all 0.3s ease;
  border-bottom: solid 0.02rem #464646;
  &::-webkit-scrollbar {
    display: none;
  }
  .content-item {
    display: flex;
    flex-direction: column;
    align-items: left;
    justify-content: center;
    .pinyin {
      display: flex;
      flex-wrap: wrap;
      margin: 0.06rem;
      margin-left: 0;
      span {
        display: block;
        width: 0.19rem;
        height: 0.62rem;
        text-align: center;
        color: #fff;
        box-sizing: border-box;
      }
      span.active {
        padding-bottom: 0.06rem;
        background-color: #000;
        border-bottom: solid 0.02rem #9fed51;
        box-sizing: border-box;
      }
      span.correct {
        color: #4e9309;
        background: #9fed51;
      }
      span.error {
        color: #f4b6b6;
        background: #5b1d1d;
      }
    }
  }
}
</style>

<script>
import { toRefs } from "vue";
export default {
  name: "English",
  props: {
    content: {
      type: Object,
      default: {},
    },
  },
  setup(props) {
    const { content } = toRefs(props);
    console.log("0000000000");
    return {
      content,
    };
  },
};
</script>
