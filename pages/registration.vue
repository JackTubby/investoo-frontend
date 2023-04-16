<template>
    <section class="text-center min-h-screen">
        <!-- Heading -->
        <h1 class="text-3xl mt-40">Registration</h1>
        <div class="flex justify-center">
            <div v-if="!loading" class="hide">
                <form class="text-center" @submit.prevent="handleSubmit">
                    <!-- First name -->
                    <input type="text" placeholder="First Name"
                        class="block border-2 border-gray-300 my-10 w-80 h-10 p-4 rounded-3xl focus:outline-indigo-400 font-thin"
                        required pattern="^[a-zA-Z\-]+$" maxlength="30" min="1" title="Your name must only contain letters"
                        v-model="form.fname">
                    <!-- Last name -->
                    <input type="text" placeholder="Last Name"
                        class="block border-2 border-gray-300 my-10 w-80 h-10 p-4 rounded-3xl focus:outline-indigo-400 font-thin"
                        required pattern="^[a-zA-Z\-]+$" max="30" min="1" title="Your name must only contain letters"
                        v-model="form.lname">
                    <!-- Email -->
                    <input type="email" placeholder="Email"
                        class="block border-2 border-gray-300 my-10 w-80 h-10 p-4 rounded-3xl focus:outline-indigo-400 font-thin"
                        required v-model="form.email">
                    <!-- Phone number -->
                    <input type="tel" placeholder="Phone Number"
                        class="block border-2 border-gray-300 my-10 w-80 h-10 p-4 rounded-3xl focus:outline-indigo-400 font-thin"
                        required pattern="^(?:0|\+?44)(?:\d\s?){9,10}$"
                        title="Your number must be a valid UK phone number and start with 44 or 0" v-model="form.phone">
                    <!-- Password -->
                    <input type="password" placeholder="Password"
                        class="block border-2 border-gray-300 my-10 w-80 h-10 p-4 rounded-3xl focus:outline-indigo-400 font-thin"
                        required v-model="form.password">
                    <!-- Confirm password -->
                    <input type="password" placeholder="Confirm Password"
                        class="block border-2 border-gray-300 my-10 w-80 h-10 p-4 rounded-3xl focus:outline-indigo-400 font-thin"
                        required v-model="form.confirmPassword">

                    <!-- Submit btn -->
                    <button
                        class="rounded-3xl hover:bg-white hover:text-black hover:border-2 hover:border-indigo-400 py-4 w-32 bg-indigo-400 text-white font-medium shadow-md">
                        Submit
                    </button>
                </form>
            </div>
        </div>
        <div v-if="loading" class="loader"></div>
        <div class="mt-10 text-green-500 text-lg">{{ successMessage }}</div>
        <div class="mt-10 text-red-500 text-lg">{{ errorMessage }}</div>
    </section>
</template>

<script>
// Utility func to slow the submit of the form to test the loader...
const delay = ms => new Promise(res => setTimeout(res, ms));
export default {
    // Using the v-model on the inputs we track the content inside
    data() {
        return {
            form: {
                email: "",
                fname: "",
                lname: "",
                phone: "",
                password: "",
                confirmPassword: "",
            },
            successMessage: "",
            errorMessage: "",
            loading: false,
        }
    },
    methods: {
        async handleSubmit() {
            // Check fields are not empty
            if (!this.form.email || !this.form.fname || !this.form.lname || !this.form.phone || !this.form.password || !this.form.confirmPassword) {
                this.errorMessage = "Please fill in all fields";
                return;
            }
            // Name regex
            const nameRegex = /^[a-zA-Z\-']+$/; // regex to check for special characters
            // Check names are valid using test method
            if (!nameRegex.test(this.form.fname) || !nameRegex.test(this.form.lname)) {
                this.errorMessage = "Please only use letters in your first and last name";
                return;
            }
            // Email regex
            const emailRegex = /\S+@\S+\.\S+/;
            // Check email is valid using test method
            if (!emailRegex.test(this.form.email)) {
                this.errorMessage = "Please enter a valid email address";
                return;
            }
            // Phone number regex
            const phoneRegex = /^(?:0|\+?44)(?:\d\s?){9,10}$/;
            // Check phone number is valid using test method
            if (!phoneRegex.test(this.form.phone)) {
                this.errorMessage = "Please enter a valid UK phone number starting with 44 or 0";
                return;
            }
            // Check passwords match
            if (this.form.password !== this.form.confirmPassword) {
                this.errorMessage = "Passwords do not match";
                return;
            }

            // If we get this far there should be no errors so reset error msg
            this.errorMessage = ""
            // Set loading to true
            this.loading = true
            // Delay form for 5s
            await delay(3000);
            // Submit form data to console
            if (!this.error) {
                console.log("First Name: ", this.form.fname)
                console.log("Last Name: ", this.form.lname)
                console.log("Email: ", this.form.email)
                console.log("Phone: ", this.form.phone)
                console.log("Submitted")
                // Set loading to false & display form submission success
                this.loading = false
                this.successMessage = "Form Submitted"
                return
            }
            else {
                this.errorMessage = "There was an error submitting this form"
                return
            }
        }
    }
}
</script>

<style>
.loader {
    margin-top: 120px;
    width: 48px;
    height: 48px;
    border: 5px solid #FFF;
    border-bottom-color: #8d63d1;
    border-radius: 50%;
    display: inline-block;
    box-sizing: border-box;
    animation: rotation 1s linear infinite;
}

@keyframes rotation {
    0% {
        transform: rotate(0deg);
    }

    100% {
        transform: rotate(360deg);
    }
}
</style>