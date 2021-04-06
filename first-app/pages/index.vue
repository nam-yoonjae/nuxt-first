<template>
  <div class="container">
    <div>
      <h1>Index.vue</h1>
      <p>1. nuxt.config.js 에서 ssr (server side rendering) 옵션을 true/false로 줄 수 있다.</p>
      <p>2. This page is rendered on the <strong>{{ rendering }}</strong></p>
      <p v-if="rendering === 'server'">
        (server side 에서 첫번째로 load 또는 새로고침 되었습니다.)
      </p>
      <p v-if="rendering === 'client'">(client side 에서 렌더링됨.)</p>
      <p>3. 링크는 NuxtLink to 를 이용한다</p>
      <h2><NuxtLink to="/dynamic">동적 페이지 생성 예제</NuxtLink></h2>
    </div>
  </div>
</template>

<script>
export default {
  asyncData() {
    return {
      rendering : process.server ? 'server' : 'client'
    }
  }
}
</script>