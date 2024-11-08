<template>
    <section class="text-white mt-20" id="contact">
        <h2 class="text-4xl font-bold text-white text-left mb-4 px-4 xl:pl-16">Let's Connect</h2>
        <div class="grid md:grid-cols-2 gap-4 relative px-4 xl:px-16 mt-8" data-aos="zoom-in-up">
            <div>
                <p class="text-[#adb7be]">I'm always excited to connect with others who are passionate about technology
                    and innovation. Whether you have a project in mind, need assistance with IT challenges, or just want
                    to chat about the latest trends in tech, I’d love to hear from you. Feel free to reach out—I’m
                    looking forward to connecting with you!
                </p>
                <div class="col-lg-4 col-md-4 mb-lg-0 mt-5">
                    <div class="flex mb-10 items-center">
                        <div class="p-2"
                            style="background: #111a3e; width: 50px;height: 46px; display: flex;justify-content: center; border-radius: 50%;
                        overflow: hidden;border: 1px solid#111a3e;backdrop-filter: blur(9px);-webkit-backdrop-filter: blur(9px);">
                            <img src="https://img.icons8.com/?size=100&id=HOE5nxXqSMWa&format=png&color=FFFFFF"
                                alt="new-post" class="w-6">
                        </div>
                        <div class="ml-5 text-white">
                            <h4>G-mail</h4>
                            <p>romanosorio121@gmail.com</p>
                        </div>
                    </div>
                    <div class="flex mb-10 items-center">
                        <div class="p-2"
                            style="background: #111a3e; width: 50px;height: 46px; display: flex;justify-content: center; border-radius: 50%;
                        overflow: hidden;border: 1px solid#111a3e;backdrop-filter: blur(9px);-webkit-backdrop-filter: blur(9px);">
                            <img src="https://img.icons8.com/ios-filled/50/ffffff/phone.png" alt="phone" class="w-6">
                        </div>
                        <div class="ml-5 text-white">
                            <h4>Phone</h4>
                            <p>+63938-210-6991</p>
                        </div>
                    </div>
                    <div class="flex mb-10 items-center">
                        <div class="p-2"
                            style="background: #111a3e; width: 50px;height: 46px; display: flex;justify-content: center; border-radius: 50%;
                        overflow: hidden;border: 1px solid#111a3e;backdrop-filter: blur(9px);-webkit-backdrop-filter: blur(9px);">
                            <img src="https://img.icons8.com/?size=100&id=dCRS0LsfeSHc&format=png&color=FFFFFF"
                                alt="linkedin" class="w-6">
                        </div>
                        <div class="ml-5 text-white">
                            <h4>Facebook</h4>
                            <a href="https://www.facebook.com/romantiko2" target="_blank" class="text-[#adb7be] underline">
                               www.FaceBook.com
                            </a>
                        </div>
                    </div>
                </div>
            </div>
            <div style="background: #111a3e; width: 100%;height: 100%; border-radius: 20px;
            overflow: hidden;border: 1px solid #111a3e;backdrop-filter: blur(9px);-webkit-backdrop-filter: blur(9px);">
                <form @submit.prevent="checkForm" class="flex flex-col p-2" data-aos="zoom-in-up">
                    <div class="mb-6">
                        <label for="email" class="text-white block mb-2 text-sm font-medium">Email</label>
                        <input type="email" id="email"
                            class="bg-[#111827] placeholder:[#9CA2A9] text-gray-100 text-sm rounded-lg block w-full p-2.5"
                            placeholder="email@gmail.com" name="email" v-model="form.email" required>
                    </div>
                    <div class="mb-6">
                        <label for="subject" class="text-white block mb-2 text-sm font-medium">Subject</label>
                        <input type="text" id="subject"
                            class="bg-[#111827] placeholder:[#9CA2A9] text-gray-100 text-sm rounded-lg block w-full p-2.5"
                            placeholder="Subject" name="subject" v-model="form.subject" required>
                    </div>
                    <div class="mb-6">
                        <label for="message" class="text-white block mb-2 text-sm font-medium">Message</label>
                        <textarea id="message"
                            class="bg-[#111827] placeholder:[#9CA2A9] text-gray-100 text-sm rounded-lg block w-full p-2.5"
                            placeholder="Let's talk about ..." name="message" v-model="form.message" required></textarea>
                    </div>
                    <button
                        class="z-1 w-[100%!important] px-6 md:px-7 py-3 rounded-full sm:w-max flex justify-center text-white bg-primary border-2 border-transparent">
                        Send Message
                    </button>
                </form>
            </div>
            <div class="bg-gradient-to-tr opacity-25 from-[#570cac] to-primary blur-2xl h-20 w-80 z-0 absolute -top-1/2 -left-4 transform -translate-x-2/3 
        -translate-1/2
        "></div>
        </div>
    </section>
</template>

<script>
export default {
    data() {
        return {
            form: {
                email: '',
                subject: '',
                message: ''
            }
        };
    },
    methods: {
        checkForm() {
            const emailPattern = /^[a-z0-9._%+-]+@[a-z0-9.-]+\.[a-z]{2,}$/;
            const subjectPattern = /^.{1,25}$/; // 1 to 25 characters
            const messagePattern = /^.{1,100}$/; // 1 to 100 characters

            if (!emailPattern.test(this.form.email) || 
                !subjectPattern.test(this.form.subject) || 
                !messagePattern.test(this.form.message)) {
                alert("Please fill up the form correctly.");
            } else {
                alert("Message sent! Thank you!");
                // Reset the form fields after submission
                this.form.email = '';
                this.form.subject = '';
                this.form.message = '';
                // Optionally, navigate back to the top of the page or another action
                window.scrollTo(0, 0); // Scroll to the top
            }
        }
    }
};
</script>
