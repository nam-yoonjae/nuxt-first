<template>
  <div class="container">
    <div>
      <h1>Index.vue</h1>
      <p>- page 디렉토리의 index.vue 파일은 welcome page 역할을 한다.</p>
      <p>- nuxt.config.js 에서 ssr (server side rendering) 옵션을 true/false 줄 수 있다.</p>
      <p>- This page is rendered on the <strong>{{ rendering }}</strong></p>
      <span v-if="rendering === 'server'">
        - server side 에서 load 또는 새로고침 되었습니다.
      </span>
      <span v-if="rendering === 'client'">
        - client side 에서 렌더링됨.
      </span>
      <p>- 링크는 NuxtLink to 를 이용한다</p>
      <h2><NuxtLink to="/dynamic">동적 페이지 생성 예제</NuxtLink></h2>
    </div>
  </div>
</template>

<script>
export default {
  asyncData() {
    if(process.server) {
      console.log('Server Side Renderd')
    } 
    if(process.client) {
      console.log('Client Side Renderd')
    }
    return {
      rendering : process.server ? 'server' : 'client'
    }
  }
}
</script>