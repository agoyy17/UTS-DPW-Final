<template>
    <div>
        <div class="container">
          <div class="row">
                <div class="mr40 mt20">
                    <router-link to="/list-product">
                        <img src="../../assets/icons/back.svg">
                    </router-link>
                </div>
                <div>
                    <h1 class="m0">Detail Product</h1>
                    <p class="mt5 mb20 tc-green">Your product detail</p>
                </div>
            </div>
            <hr class="uline-grey">
            <div class="mt50 row">
                    <div class="w50">
                      <img :src="require(`../../assets/images/${item.productI}`)" width="400" alt="Nama Gambar" />
                        <br>
                         <table>
                            <tr>
                                <td><b>Status</b></td>
                                <td><b>Product Status</b></td>

                            </tr>
                            <tr>
                                <td><div v-if="item.status === 1">
                                    <label class="label-green">Publish</label>
                                </div>
                                <div v-if="item.status === 2">
                                    <label class="label-red">Private</label>
                                </div></td>
                                <td><div v-if="item.productS === 1">
                                    <label class="label-green">Availability</label>
                                </div>
                                <div v-if="item.productS === 2">
                                    <label class="label-red">Sold</label>
                                </div></td>
                            </tr>
                         </table>
                    </div>
                    <div class="w40 pl40">
                        <p class="text-muted">#{{ item.productC }}</p>
                        <h1>{{ item.productN }}</h1>
                        <h1>Rp {{ item.price }}</h1>
                        <h3>Product Description : </h3>
                        <p class="text-muted">{{ item.productDescription }}</p>
                        <h3>Product Categories: {{ item.productCt }}</h3>
                        <h3>Unit: {{ item.unit }}</h3>
                        <h3>Min Purchase: {{ item.productMinPurchase }} Unit</h3>
                        <h3>Max Purhcase: {{ item.productMaxPurchase }} Unit</h3>

                    </div>

            </div>
        </div>
    </div>

</template>
<script>
import Menu from "../../components/menu.vue";

export default {
    name: "list-product",
    components: {
        Menu,
    },
    data() {
        return {
            list_product: [
            {
                    id: "1",
                    productC: "j4f7ewf36",
                    productN: "iPhone 15 128GB",
                    price: "15.000.000",
                    status: 1,
                    productDescription: "Ios 17",
                    productCt: "Electronic",
                    unit: "20",
                    productMinPurchase: "1",
                    productMaxPurchase: "18",
                    productS: 1,
                    productI : "iphone15.png",
                },
                {
                    id: "2",
                    productC: "dayx632b1",
                    productN: "iPhone 14 128GB",
                    price: "12.500.000",
                    status: 1,
                    productDescription: "Ios 17",
                    productCt: "Electronic",
                    unit: "17",
                    productS: 1,
                    productI : "iPhone14.png"
                }
            ],
            item: null,
        };
    },
    created() {
        // Mendapatkan parameter ID dari URL
        const productId = this.$route.params.id;

        // Mencari produk berdasarkan ID yang diberikan
        this.item = this.list_product.find(
            (product) => product.id === productId
        );
    },
};
</script>