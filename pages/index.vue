<template>
    <!-- hero section -->
    <section class="text-center bg-gray-500 py-24">
        <h1 class="text-5xl py-5 text-white">I'm A Hero</h1>
        <h2 class="text-2xl pb-5 text-white">Register Here</h2>
        <NuxtLink to="/registration">
            <button
                class="bg-indigo-400 p-4 rounded-3xl text-white w-32 hover:bg-white hover:text-indigo-400 shadow-xl">Register</button>
        </NuxtLink>
    </section>
    <!-- Features section -->
    <section class="mt-10">
        <h2 class="text-3xl text-center">Features</h2>
        <div class="lg:flex text-center justify-center">
            <!-- Feature one -->
            <Feature title="Feature #1" icon="ICON" desc="Lorem ipsum dolor sit amet, consectetur adipisicing
                                        elit. Laborum, nam? Ut vel, voluptatibus delectus
                                        harum a asperiores."></Feature>
            <!-- Feature two -->
            <Feature title="Feature #2" icon="ICON" desc="Lorem ipsum dolor sit amet, consectetur adipisicing
                                        elit. Laborum, nam? Ut vel, voluptatibus delectus
                                        harum a asperiores."></Feature>
            <!-- Feature three -->
            <Feature title="Feature #3" icon="ICON" desc="Lorem ipsum dolor sit amet, consectetur adipisicing
                                        elit. Laborum, nam? Ut vel, voluptatibus delectus
                                        harum a asperiores."></Feature>
        </div>
    </section>
    <!-- Pricing section -->
    <section class="mt-10">
        <h2 class="text-3xl text-center sm:py-6 md:py-0">Pricing</h2>
        <div class="lg:flex text-center justify-center font-light">
            <!-- Price 1 -->
            <Pricing title="Basic" icon="ICON" :price=10 :url="'/registration'"
                :features="['Lorem, ipsum dolor. 1', 'Lorem, ipsum dolor. 2', 'Lorem, ipsum dolor. 3',]"></Pricing>
            <!-- Price 2 -->
            <Pricing title="Standard" icon="ICON" :price=20 :url="'/registration'"
                :features="['Lorem, ipsum dolor. 1', 'Lorem, ipsum dolor. 2', 'Lorem, ipsum dolor. 3',]"></Pricing>
            <!-- Price 3 -->
            <Pricing title="Premium" icon="ICON" :price=30 :url="'/registration'"
                :features="['Lorem, ipsum dolor. 1', 'Lorem, ipsum dolor. 2', 'Lorem, ipsum dolor. 3',]"></Pricing>
        </div>
    </section>
</template>

<script>
// Import components
import Pricing from "../components/Pricing.vue"
import Feature from "../components/Features.vue";
export default {
    components: {
        Feature,
        Pricing,
    },
};
definePageMeta({
    layout: "default"
})
</script>

<style></style>