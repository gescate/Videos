<template >
    <article>
        <iframe width="560" height="315" :src="data.url" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen>
        </iframe>
        <h2>{{data.title}}</h2>
        <p>{{data.description}}</p>
    </article>
</template>
<script>
export default {
    name: 'Card',
    props: {
        data: {
            type: Object,
        },
    }
    
}
</script>
<style lang="">
    
</style>