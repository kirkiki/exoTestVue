<template>
    <v-btn @click="checkAnswer(isTrue)" :color="color">{{text}}</v-btn>
</template>

<script>
import { setTimeout } from 'timers';
export default {
    props: ["isTrue" , "text"],
    data() {
        return {
            isClicked: false,
            color: ""
        }
    },
    methods: {
        checkAnswer : function(bool){
            bool == "true" ? this.color = "success" : this.color = "error"
            setTimeout(() => {
                this.$emit('change')
            }, 1000); 
        }
    },
}
</script>