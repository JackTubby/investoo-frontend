<template>
            <div
                class="border-2 border-solid rounded-3xl bg-gradient-to-r from-indigo-400 to-green-400 shadow-2xl w-80 h-80 m-auto my-4 lg:m-10 p-2">
                <div class="pb-4">{{ icon }}</div>
                <div class="text-white pb-6">
                    <h3 class="pb-4 text-xl ">{{ title }}</h3>
                    <p class="text-2xl pb-5">£{{ price }}</p>
                    <ul class=" space-y-1">
                        <li v-for="feature in features" :key="feature">{{ feature }}</li>
                    </ul>
                </div>
                <NuxtLink :to="url"><button
                        class="rounded-3xl bg-white p-2 w-32 hover:bg-indigo-400 hover:text-white font-medium shadow-md">Register
                        Now</button></NuxtLink>
            </div>
</template>

<script>
export default {
    props: {
        title: {
            type: String,
            required: true
        },
        icon: {
            type: String,
            required: true
        },
        price: {
            type: Number,
            required: true
        },
        url: {
            type: String,
            required: true
        },
        features: {
            type: Array,
            required: true
        },
    },
};
</script>