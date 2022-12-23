<template>
    <div class="conversor">
        <h2>{{ moedaA }} Para {{ moedaB }}</h2>
        <input type="text" v-model="moedaA_value" v-bind:placeholder="moedaA" id="valor">
        <input type="button" value="Converter" @click="converter" >
        <h2>{{ moedaB_value }}</h2>
    </div>
</template>

<script>

export default {
    name: "ConversorMoeda",
    props: ["moedaA", "moedaB"],
    data() {
        return {
            moedaA_value: "",
            moedaB_value: 0
        }
    },
    methods: {
        converter() {
            let url = "https://economia.awesomeapi.com.br/json/last/USD-BRL"
            fetch(url)
                .then((res) => {
                    return res.json()
                })
                .then((data) => {
                    let input = document.getElementById("valor")
                    console.log(input)
                    let valor = input.value
                    console.log(valor)
                    let cotacao = data.USDBRL.ask
                    console.log(cotacao)
                    if (valor != "" && valor > 0) {
                        this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(2)
                        console.log("if")
                    } else {
                        this.moedaB_value = "Não possivel converter valor negativo ou vazio"
                        console.log("else")
                    }

                })
        }
    }
}

</script>


<style scoped>

</style>