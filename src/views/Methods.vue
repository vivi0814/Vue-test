<template>
    <div class="intro">
        <h1>Vue---intro</h1>
        <h3>methods</h3>
        <p>同程式片段重複出現三次或以上的時候，在重構時我們就會將重複的部分提取出來並包裝成函式以便重複使用。</p>
    </div>
    <div >
        <!-- =============methods寫法============== -->
        <!-- <p>總金額共{{subtotal()}}元</p>
        <p>總金額共{{subtotal()}}元</p>
        <p>總金額共{{subtotal()}}元</p> -->

        <!-- ===========computed寫法============ -->
        <!-- <p>總金額共{{subtotal}}元</p>
        <p>總金額共{{subtotal}}元</p>
        <p>總金額共{{subtotal}}元</p> -->

        <!-- =============computed 用v-for寫法=============== -->
        <p v-for="(item, index) in items" :key="item.id">總金額共{{subtotal [index]}}</p>    

    </div>
</template>

<script>
export default{
    data() {
        return{
            items:[
                {
                    id:1,
                    price:100,
                    quantity:10,
                },
                {
                    id:2,
                    price:50,
                    quantity:12,
                },
                {
                    id:3,
                    price:10,
                    quantity:20,
                },

            ]
            
        };
    },
    // methods:{
    //     subtotal(){
    //         return this.price * this.quantity;
    //     }
    // },

    // computed: {
    //     subtotal() {
    //     return this.price * this.quantity;
    //     }
    // }

    computed: {
        subtotal() {
        return this.items.map(item => item.price * item.quantity);
        },
    }

}
</script>