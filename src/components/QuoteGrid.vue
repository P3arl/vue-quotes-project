<template>
    <div class="row">
        <app-Quote v-for="(quote, index) in quotes" :key="quote"
        @click.native="deleteQuote(index)"
        >
            {{ quote }}
        </app-Quote>
    </div>
</template>

<script>
import Quote from './Quote.vue'

export default {
    props: ['quotes'],
    methods: {
        deleteQuote(index) {
            this.$emit('quoteDeleted', index)
        }
    },
    components: {
        appQuote: Quote
    }
}
</script>

<style scoped>

</style>