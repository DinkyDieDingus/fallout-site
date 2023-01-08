<script>
export default {
    props: ['name', 'links']
}
</script>

<template>
    <div>
        <h1>{{ name }}</h1>
        <ul>
            <li v-for="link in links">
                <template v-if="link.icon">
                    <font-awesome-icon :icon="[link.iconIsBrand ? 'fab' : 'fas', link.icon]"/>&nbsp;
                </template>
                <a v-bind:href="link.url" target="_blank" rel="noopener noreferrer">{{ link.name }}</a>
            </li>
        </ul>
    </div>
</template>

<style scoped>
    a {
        color: inherit;
    }

    ul {
        list-style-type: none;
        margin-left: -20pt;
    }
</style>