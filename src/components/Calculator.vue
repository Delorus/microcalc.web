<template>
    <div class="border container">
            <label for="result">Result: </label>
            <input type="text" id="result" v-model="expr" v-on:keyup.enter="calculate">
            <button v-on:click="calculate">=</button>
    </div>
</template>

<script>
    export default {
        name: "Calculator",
        props: {
            expr: String
        },
        methods: {
            calculate() {
                const expr = this.expr;
                this.expr = eval(expr);
            }
        }
    }
</script>

<style scoped>
    .border {
        border: 1px solid black;
        border-radius: 5px;
        box-shadow: 0 0 10px rgba(0,0,0,0.5);
    }
    .container {
        padding: 0.5em;
        text-align: center;
        display: inline-block;
    }
</style>
