<script setup>
import { ref } from 'vue';

const menuButtons = ref([
    {
        label: 'Lorem'
    },
    {
        label: 'Ipsum'
    }
])
function scrollToOption(element){
    if(element.label == 'Lorem'){
        window.scrollTo({
            top: document.getElementById('lorem').offsetTop,
            left: 0,
            behavior: "smooth",
        });
    }
    else{
        window.scrollTo({
            top: document.getElementById('ipsum').offsetTop,
            left: 0,
            behavior: "smooth",
        });
    }
}
</script>

<template>
    <div class="header">
        <div class="container">
            <div class="columns">
                <div class="column is-half alignedMobile">
                    <h2 class="pretendToLogo">
                        Logo
                    </h2>
                </div>
                <div class="column is-half alignedToEnd">
                    <p
                    v-for="(options, index) in menuButtons"
                    @click="scrollToOption(options)"
                    class="font-options-menu">
                        {{ options.label }}
                    </p>
                </div>
            </div>
        </div>
    </div>
    <div>
        <slot/>
    </div>
</template>