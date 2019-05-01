<template>
    <div>
        <h3>Some texts.... testing</h3>
        <p v-for="(text, i) in texts" :key="i">{{ text }}</p>
    </div>
</template>
<script>
    export default {
        data() {
            return {
                texts: [],
            }
        },
        created() {
            this.getTexts();
        },
        methods: {
            getTexts() {
                fetch('/api/texts')
                    .then(re => re.json())
                    .then(data => this.texts = data.texts);
            }
        }
    }
</script>