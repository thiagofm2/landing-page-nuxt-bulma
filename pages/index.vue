<script setup>
import header from '../components/header.vue';
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
        top: document.getElementById('form').offsetTop,
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
        <div class="first-row alignVertical">
        <header/>

            <div class="container ">
                <div class="columns">
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
                        <div>
                            <h1 class="titleSection">
                                Lorem
                            </h1>
                            <div class="line-separator"/>
                            <p>
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit,
                                sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris
                                nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in
                                reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
                                pariatur. Excepteur sint occaecat cupidatat non proident, sunt in
                                culpa qui officia deserunt mollit anim id est laborum.
                            </p>
                            <button
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
                        src="../assets/banner-vertical.png"
                        />
                        <img
                        class="position-image-gallery"
                        src="../assets/banner-vertical2.png"
                        />
                    </div>
                </div>
            </div>
        </div>

        <div class="section" style="padding-bottom:0px">
            <div class="row-input" id="form">
                <div class="container">
                    <div class="columns">
                        <div class="column is-half alignedToTop">
                            <div class="input-infos">
                                <h1 class="titleSection-input">
                                    Ipsum
                                </h1>
                                <div class="line-separator-input"/>
                                <p style="color:#d8d8d8">
                                    Lorem ipsum dolor sit amet, consectetur adipiscing elit,
                                    sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris
                                    nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in
                                    reprehenderit in voluptate velit esse cillum.
                                </p>
                            </div>
                        </div>
                        <div class="column is-half alignToCenter">
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
    </div>
</template>