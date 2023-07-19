<template>
    <div>
        <h4>{{ Title }}</h4>
        <input v-model="inputData" @input="onChange" :placeholder="Placeholder"/>
    </div>
</template>

<script>
export default {
    name: "InputForm",
    emits: ['input-change'],
    data() {
        return {
            inputData: "",
        }
    },
    props: {
        Title: {
            type: String,
            required: true,
        },
        Placeholder: {
            type: String,
            required: true,
        },
    },
    methods: {
        onChange() {
            this.$emit('input-change', {
                title: this.Title,
                value: this.inputData
            });
        }
    }
};
</script>
