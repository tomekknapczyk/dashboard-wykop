<template>
    <div class="max-w-md mx-auto">
        <div class="max-w">
            <h1 class="title text-center text-2xl font-semibold border-b mb-3">
                Hot Mirko
            </h1>

            <article v-for="article in articles" class="mb-4 shadow-lg">

                <img v-if="article.embed" :src="article.embed.preview" class="mx-auto w-full h-auto">
                <p class="text-center font-semibold leading-loose text-sm text-gray-500 bg-black border-t border-gray-600">{{ article.body.text }}</p>
            </article>
        </div>
    </div>
</template>

<script>
    import axios from '~/plugins/axios'

    export default {
        async asyncData () {
            const { data } = await axios.get('/Entries/Hot/period/6/output/both/appkey/mcsj9tZUp0/')
            return { articles : data.data}
        }
    }
</script>
