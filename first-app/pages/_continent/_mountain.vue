<template>
    <div class="container">
        <p><NuxtLink to="/dynamic">Back to Mountains</NuxtLink></p>
        <p><NuxtLink to="/rivers">Rivers</NuxtLink></p>
        <h1>Continent : {{ continent }}</h1>
        <h2>Mountain : {{ mountain }}</h2>
        <p>Path : {{ $route.path }}</p>
    </div>
</template>
<script>
export default {
    async asyncData({ params, redirect }) {
        const mountains = await fetch (
            'https://api.nuxtjs.dev/mountains'
        ).then((res) => res.json())

        const filteredMountain = mountains.find(
            (el) => 
            el.continent.toLowerCase() === params.continent &&
            el.slug === params.mountain
        )
        if(filteredMountain) {
            return {
                continent : filteredMountain.continent,
                mountain : filteredMountain.title
            }
        } else {
            redirect('/')
        }
    }
}
</script>