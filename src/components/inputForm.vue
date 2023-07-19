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

<style scoped>
*{
    font-family: Roboto,sans-serif;
}
h4{
    width: 8%;
    font-size: 24px;
    font-weight: 600;
    border-bottom: 4px solid #4922e3;
}
input{
    width: 25%;
    padding: 10px 5px;
    font-size: 20px;
    font-weight: 600;
    color:#17151f;
    border: 3px solid #4922e3;
    border-radius: 4px;
}
</style>
