<script setup>
import { ref } from 'vue';
import axios from 'axios';

const infosField = ref(
    {
        name:'',
        email:'',
        phone:''
    }
)

function scrollToForm(){
    window.scrollTo({
        top: document.getElementById('ipsum').offsetTop,
        left: 0,
        behavior: "smooth",
    });
}

async function simulatePost(){
    await axios.post(`/your-url`, infosField).then(() => {
        console.log('Success!')
    }).catch((error) =>{
        window.alert("It's just a fictional form!")
    })
}
</script>

<template>
    <div>
        <div class="first-row">
            <Header/>
            <div class="container ">
                <div class="columns alignVertical">
                    <div class="column is-half">
                        <h1 class="title-home">
                            Thiago Faria Moreira LP
                        </h1>
                        <p class="subtitle-first-row">
                            Hello everyone, welcome to my first test with Nuxt and Bulma CSS.
                            Full mockup from scratch so ignore some bugs (please)
                        </p>
                        <button
                        @click="scrollToForm()"
                        class="btn-first-row">
                            Go to form!
                        </button>
                    </div>
                </div>
            </div>
        </div>

        <div class="container">
            <div class="section">
                <div class="columns">
                    <div
                    class="column is-half alignedToTop"
                    >
                        <div class="sizeMobile">
                            <h1 class="titleSection" data-aos="fade-up" data-aos-delay="400">
                                Lorem
                            </h1>
                            <div class="line-separator" data-aos="fade-up" data-aos-delay="400"/>
                            <p data-aos="fade-up" data-aos-delay="400">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit,
                                sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris
                                nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in
                                reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
                                pariatur. Excepteur sint occaecat cupidatat non proident, sunt in
                                culpa qui officia deserunt mollit anim id est laborum.
                            </p>
                            <button
                            data-aos="fade-up" data-aos-delay="400"
                            @click="scrollToForm()"
                            class="btn-cta">
                                Lorem ipsum
                            </button>
                        </div>
                        <img
                        class="plaint-img"
                        src="../assets/plantaPng.png"
                        />
                    </div>
                    <div class="column is-half alignToCenter">
                        <img
                        data-aos="fade-up" data-aos-delay="400"
                        src="../assets/banner-vertical.png"
                        />
                        <img id="lorem"
                        data-aos="fade-up" data-aos-delay="900"
                        class="position-image-gallery"
                        src="../assets/banner-vertical2.png"
                        />
                    </div>
                </div>
            </div>
        </div>

        <div class="section" style="padding-bottom:0px">
            <div class="row-input" id="ipsum">
                <div class="container">
                    <div class="columns">
                        <div class="column is-half alignedToTop">
                            <div class="input-infos">
                                <h1 class="titleSection-input" data-aos="fade-up" data-aos-delay="300">
                                    Ipsum
                                </h1>
                                <div class="line-separator-input" data-aos="fade-up" data-aos-delay="400"/>
                                <p style="color:#d8d8d8" data-aos="fade-up" data-aos-delay="500">
                                    Lorem ipsum dolor sit amet, consectetur adipiscing elit,
                                    sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris
                                    nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in
                                    reprehenderit in voluptate velit esse cillum.
                                </p>
                            </div>
                        </div>
                        <div class="column is-half alignToCenter" data-aos="fade-in" data-aos-delay="800">
                            <div class="card-input alignToCenter">
                                <input
                                v-model="infosField.name"
                                placeholder="Name"
                                class="input-field"/>
                                <input
                                v-model="infosField.email"
                                placeholder="E-mail"
                                class="input-field"/>
                                <input
                                v-model="infosField.phone"
                                placeholder="Phone"
                                class="input-field"/>
                                <button
                                @click="simulatePost()"
                                class="btn-input">
                                    Lorem ipsum
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <Footer/>
    </div>
</template>