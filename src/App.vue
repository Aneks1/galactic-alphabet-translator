<template>
    <div class="abody">    
        <span class="font-6vh weight-600 text-center">Galactic Alphabet Translator</span>
        <div class="row justify-space-between align-center width-95vw height-45vh">
            <textarea v-model="text" placeholder="Hello World" class="bg-blue padding-3 border-box radius-2vh width-45 height-100 font-3vh"/>
            <div class="padding-3 border-box radius-2vh width-45 height-100 bg-blue">
                <span class="font-3vh">{{ translation }}</span>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'Translator',
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

            const array = this.text.split('')

            console.log(array)
            for(const char of array) {

                switch (char.toLowerCase()) {

                    // Ye its just that, what did you expect? Well, I can avoid weird bugs like this, like you can add ñ and it just skips it, with other methods it will just break. Woah that was a lot of text.

                    case 'a':
                        this.translation += 'ᔑ'
                        break
                    case 'b':
                        this.translation += 'ʖ'
                        break
                    case 'c':
                        this.translation += 'ᔮ'
                        break
                    case 'd':
                        this.translation += '↸'
                        break
                    case 'e':
                        this.translation += 'ᒷ'
                        break
                    case 'f':
                        this.translation += '⎓'
                        break
                    case 'g':
                        this.translation += '┤'
                        break
                    case 'h':
                        this.translation += '⍑'
                        break
                    case 'i':
                        this.translation += '╎'
                        break
                    case 'j':
                        this.translation += '⋮'
                        break
                    case 'k':
                        this.translation += 'ꖌ'
                        break
                    case 'l':
                        this.translation += 'ꖎ'
                        break
                    case 'm':
                        this.translation += 'ᒲ'
                        break
                    case 'n':
                        this.translation += 'リ'
                        break
                    case 'o':
                        this.translation += '𝙹'
                        break
                    case 'p':
                        this.translation += '¡!'
                        break
                    case 'q':
                        this.translation += 'ᑑ'
                        break
                    case 'r':
                        this.translation += '∷'
                        break
                    case 's':
                        this.translation += 'ᓭ'
                        break
                    case 't':
                        this.translation += 'ℸ'
                        break
                    case 'u':
                        this.translation += '⚍'
                        break
                    case 'v':
                        this.translation += '⍊'
                        break
                    case 'w':
                        this.translation += '∴'
                        break
                    case 'x':
                        this.translation += ' ̇/'
                        break
                    case 'y':
                        this.translation += '||'
                        break
                    case 'z':
                        this.translation += '∩'
                        break
                    case ' ':
                        this.translation += String.fromCharCode(160)
                        break
                    default: 
                        this.translation += char
                        break
                }
            }

            console.log(this.translation)
        }
    }
})
</script>

<style>
    @import "../public/css/main.css";
</style>