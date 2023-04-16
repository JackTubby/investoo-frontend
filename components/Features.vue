<template>
    <div class="border-2 border-solid rounded-3xl w-80 h-80 m-auto my-4 lg:m-10 p-2 shadow-xl lg:shadow-2xl">
        <div class="py-6">{{ icon }}</div>
        <div class="pt-4">
            <h3 class="font-bold text-lg pb-6">{{ title }}</h3>
            <p class="text-sm lg:text-base p-2 text-gray-500 font-light ">{{ desc }}</p>
        </div>
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
        desc: {
            type: String,
            required: true
        },
    },
};
</script>