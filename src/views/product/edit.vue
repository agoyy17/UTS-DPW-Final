<template>
    <div v-if="item">
        <div class="container">
            <div class="row">
                <div class="mr40 mt20">
                    <router-link to="/list-product">
                        <img src="../../assets/icons/back.svg">
                    </router-link>
                </div>
                <div>
                    <h1 class="m0">Add Product</h1>
                    <p class="mt5 mb20 tc-green">Add new Product to help you do it as soon as possible</p>
                </div>
            </div>
            <hr class="uline-grey">
            <div class="mt30 row">
                <div class="w20">
                    <label class="form-label">Product Images</label>
                </div>
                <div class="w80">
                    <img :src="require(`../../assets/images/${item.productI}`)" width="65" alt="Nama Gambar" />
                </div>
            </div>
            <div class="mt30 row">
                <div class="w20">
                    <label class="form-label">Product Code</label>
                </div>
                <div class="w80">
                    <input class="form-text" type="text" maxlength="8" minlength="8" v-model="item.productC" readonly disabled>
                </div>
            </div>
            <div class="mt30 row">
                <div class="w20">
                    <label class="form-label">Product Name</label>
                </div>
                <div class="w80">
                    <input class="form-text" type="text" placeholder="Product Name" maxlength="20" minlength="5" v-model="item.productN">
                </div>
            </div>
            <div class="mt30 row">
                <div class="w20">
                    <label class="form-label">Product Price</label>
                </div>
                <div class="w80">
                    <input class="form-text" type="text" placeholder="Product Price" v-model="item.price">
                </div>
            </div>
            <div class="mt30 row">
                <div class="w20">
                    <label class="form-label">Product Description</label>
                </div>
                <div class="w80">
                    <textarea class="form-text" cols="20" rows="5" placeholder="Masukkan Product Description" v-model="item.productDescription"></textarea>
                </div>
            </div>
            <div class="mt30 row">
                <div class="w20">
                    <label class="form-label">Product Unit</label>
                </div>
                <div class="w80">
                    <input class="form-text" type="number" placeholder="Product Unit" v-model="item.unit">
                </div>
            </div>
            <div class="mt30 row">
                <div class="w20">
                    <label class="form-label">Min Purchase</label>
                </div>
                <div class="w80">
                    <input class="form-text" type="number" placeholder="Masukkan Min Purchase" v-model="item.productMinPurchase">
                </div>
            </div>
            <div class="mt30 row">
                <div class="w20">
                    <label class="form-label">Maximal Purchase</label>
                </div>
                <div class="w80">
                    <input class="form-text" type="number" placeholder="Masukkan Max Purchase" v-model="item.productMaxPurchase">
                </div>
            </div>
            <div class="mt30 row">
                <div class="w20">
                    <label class="form-label">Categories</label>
                </div>
                <div class="w80">
                    <select class="form-select">
                        <option disabled>--- Select Categories ---</option>
                        <option value="1" selected>Electronic</option>
                        <option value="2">Vehicle</option>
                    </select>
                </div>
            </div>

            <div class="flex mt30">
                <router-link to="/list-product">
                    <button class="bt-submit-green">Update Product</button>
                </router-link>
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
                    productMinPurchase: "1",
                    productMaxPurchase: "10",
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