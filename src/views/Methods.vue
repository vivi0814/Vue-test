<template>
    <div class="intro">
        <h1>methods應用</h1>
        <p>同程式片段重複出現三次或以上的時候，在重構時我們就會將重複的部分提取出來並包裝成函式以便重複使用。</p>
    </div>
    <div id="app">
        <p>總金額共{{subtotal()}}元</p>
        <p>總金額共{{subtotal()}}元</p>
        <p>總金額共{{subtotal()}}元</p>
    </div>
</template>

<script>
export default{
    data() {
        return{
            price:100,
            quantity:10
        };
    },
    methods:{
        subtotal(){
            return this.price * this.quantity;
        }
    }

}
</script>