<template>
    <div>
        <h1>about.vue</h1>
        <p>- nuxt.config.js 에서 ssr (server side rendering) 옵션을 true/false 줄 수 있다.</p>
        <p>-  이 페이지는 <strong>{{ rendering }}</strong> 에 의해 렌더링되었습니다.</p>
        <span v-if="rendering === 'server'">
            - server side 에서 load 또는 새로고침 되었습니다.
        </span>
        <span v-if="rendering === 'client'">
            - client side 에서 렌더링됨.
        </span>
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