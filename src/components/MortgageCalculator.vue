<template>
    <div class="form" v-if="(credit!==null || credit!==0) && (percent!==null || percent!==0) && (period!==null || period!==0)">
        <div class="form__block">
            <h3 class="form__text">Сумма кредита</h3>
            <input type="number" class="form__credit" v-model="credit">
        </div>
        <div class="form__block">
            <h3 class="form__text">Желаемый процент</h3>
            <input type="number" class="form__percent" v-model="percent">
        </div>
        <div class="form__block">
            <h3 class="form__text">Период заема в годах</h3>
            <input type="number" class="form__period" v-model="period">
        </div>
    </div>
    <div class="result" v-else>
        <div class="form__block">
            <p class="result__text">Ежемесячный платеж:</p>
            <h3 class="result__monthly">{{ submit.monthlyPayment }}</h3>
        </div>
        <div class="form__block">
            <p class="result__text">Общая сумма платежа:</p>
            <h3 class="result__summary">{{ submit.total }}</h3>
        </div>
    </div>
</template>
<script>
export default {
    name: 'MortgageCalc',
    data() {
        return {
            credit: null,
            percent: null,
            period: null
        }
    },
    computed: {
        submit: function(){
            const principal = parseFloat(this.credit);
            const interestRate = parseFloat(this.percent) / 100 / 12;
            const loanTermMonths = parseFloat(this.period)*12;

            const numerator = principal * interestRate * Math.pow(1 + interestRate, loanTermMonths);
            const denominator = Math.pow(1 + interestRate, loanTermMonths)-1;
            const monthlyPayment = (numerator/denominator).toFixed(2);
            const total = (monthlyPayment * 12 * this.period).toFixed(2);

            return {monthlyPayment, total};

        }
    }
}
</script>
<style lang="scss">
    
</style>