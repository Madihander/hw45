<template>
    <form class="container" @submit.prevent="showData">
        <h1>Form</h1>
        <input-form v-for="input in inputs"
                    :key="input.title"
                    :Title="input.title"
                    :Placeholder="input.placeholder"
                    @input-change="collectData">
        </input-form>
        <button type="submit">Submit</button>
    </form>
    <div class="container" v-show="showInfo">
        <h1>Collect Data</h1>
        <ul>
            <li>
                <h4>Phone</h4>
                <p>{{this.data.phone}}</p>
            </li>
            <li>
                <h4>Laptop</h4>
                <p>{{this.data.laptop}}</p>
            </li>
            <li>
                <h4>Mouse</h4>
                <p>{{this.data.mouse}}</p>
            </li>
            <li>
                <h4>Earphones</h4>
                <p>{{this.data.earphones}}</p>
            </li>
            <li>
                <h4>Browser</h4>
                <p>{{this.data.browser}}</p>
            </li>
        </ul>
    </div>
</template>

<script>
import InputForm from "@/components/inputForm.vue";

export default {
    components: {
        InputForm,
    },
    data() {
        return {
            showInfo:false,
            inputs: [
                {title: "Phone", placeholder: "what is model of your Phone"},
                {title: "Laptop", placeholder: "what is model of your Laptop"},
                {title: "Mouse", placeholder: "what is model of your Mouse"},
                {title: "Earphones", placeholder: "what is model of your Earphones"},
                {title: "Browser", placeholder: "what is model of your Browser"},
            ],
            data: {
                phone: "",
                laptop: "",
                mouse: "",
                earphones: "",
                browser: "",
            },
            inputInfo:[],
        }
    },
    methods: {
        collectData(inputData) {
            if (inputData.title === "Phone"){
                this.data.phone = inputData.value
            }
            if (inputData.title === "Laptop"){
                this.data.laptop = inputData.value
            }
            if (inputData.title === "Mouse"){
                this.data.mouse = inputData.value
            }
            if (inputData.title === "Earphones"){
                this.data.earphones = inputData.value
            }
            if (inputData.title === "Browser"){
                this.data.browser = inputData.value
            }
        },
        showData(){
            this.showInfo=true

        }
    },
};
</script>
<style>
.container{
    font-family: Roboto,sans-serif;
    margin-top: 15px;
    margin-left: 15px;
    border: 3px solid #4922e3;
    padding: 10px;
}
button{
    margin-top: 15px;
    background-color: #fff;
    border: 3px solid #4922e3;
    color:#17151f;
    font-weight: 600;
    font-size: 22px;
    padding: 12px 15px;
}
h4{
    width: 8%;
    font-size: 24px;
    font-weight: 600;
    border-bottom: 4px solid #4922e3;
}
p{
    padding-left: 10px;
    font-size: 22px;
    font-weight: 600;
    border-left: 4px solid #4922e3;
}
</style>
