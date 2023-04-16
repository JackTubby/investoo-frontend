<template>
    <header>
        <nav class="md:flex md:h-24 text-center">
            <!-- <img /> -->
            <div class="pt-4 pb-10">
                <div class="absolute sm:left-20 sm:top-8 md:top-4 md:left-36 cursor-pointer sm:absolute left-0 right-0">
                    <NuxtLink to="/"><img src="../assets/default-logo.png" alt="default logo" class="w-16"></NuxtLink>
                </div>
                <div class="md:absolute md:right-72 md:space-x-8 pt-5 sm:text-center">
                    <NuxtLink to="registration" class="cursor-pointer hover:text-indigo-500 block md:inline sm:pt-3">
                        Registration</NuxtLink>
                </div>
            </div>
        </nav>
    </header>
    <slot />
    <footer class="bg-indigo-400 mt-14 text-center">
        <div class="md:flex justify-center pt-5 text-white">
            <div class="md:pr-24 space-y-1 font-thin">
                <p class="p-0">01632 960128</p>
                <p class="pb-2">lorem@ipsum.com</p>
                <p class="p-0">61 lorem lane</p>
                <p class="p-0">lorem city</p>
                <p class="p-0">WF1 65H</p>
                <p class="p-0">lorem kingdom</p>
            </div>
            <div class="sm:mt-10 md:flex justify-center sm:pt-10 md:pt-0 pb-5">
                <NuxtLink to="https://www.instagram.com/" target="_blank">
                    <button class="px-2">Instagram
                    </button>
                </NuxtLink>
                <NuxtLink to="https://facebook.com/" target="_blank">
                    <button class="px-2">Facebook
                    </button>
                </NuxtLink>
                <NuxtLink to="https://twitter.com/" target="_blank">
                    <button class="px-2">Twitter
                    </button>
                </NuxtLink>
                <NuxtLink to="https://linkedin.com" target="_blank">
                    <button class="px-2">LinkedIn
                    </button>
                </NuxtLink>
            </div>
        </div>
    </footer>
</template>