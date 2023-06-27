<template>
    <div id="container">    
        <span id="title" class="relative">Galactic Alphabet Translator</span>
        <div id="panels" class="relative">
            <textarea v-model="text" placeholder="Write something here" class="blur padding-3 border-box radius-2vh width-45 height-100 font-3vh relative"/>
            <div id="translation" class="relative blur">
                <span id="output">{{ translation }}</span>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'App',
    data() {
        return {
            text: '',
            translation: ''
        }
    },
    watch: {
        'text': function() {
            this.translate()
        }
    },
    methods: {
        translate() {
            this.translation = ''
            const array: string[] = this.text.split('')
            const letters = 'abcdefghijklmnoqrstuvwz'
            const galactic = 'ᔑʖᔮ↸ᒷ⎓┤⍑╎⋮ꖌꖎᒲリ𝙹ᑑ∷ᓭℸ⚍⍊∴∩'
            for(let char of array) {
                char = char.toLowerCase()
                if(letters.split('').includes(char)) {
                    const index = letters.split('').findIndex((x) => x == char)
                    this.translation += galactic[index]
                }
                else if(char == 'p') this.translation += '¡!'
                else if(char == 'x') this.translation += ' ̇/'
                else if(char == 'y') this.translation += '||'
                else if(char == ' ') this.translation += String.fromCharCode(160)
                else continue
            }
        }
    }
})
</script>

<style>
    @import "./styles.css";
</style>