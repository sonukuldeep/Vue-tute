<template>
    <div class="m-2 p-2">
        <h1 class="text-3xl">{{ pageTitle }}</h1>
        <p class="">{{ pageContent }}</p>
    </div>
</template>

<script>
export default {
    props: ['pageTitle', 'pageContent',], // notice how i use camel case here and kabab case when i'm passing data
    // we can also pass just page and use page.pageTitle and page.content below
}
</script>