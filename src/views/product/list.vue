<template>
    <div>
        <Menu/>
        <div class="container">
            <h1 class="m0">Product</h1>
            <div class="row">
                <div class="col">
                    <p class="mt5 mb20 tc-green">Manage your product details</p>
                </div>
                <div class="col flex">
                    <router-link to="/add-product">
                        <button class="bt-green">+ Add Product</button>
                    </router-link>
                </div>
            </div>
            <div class="row bg-blue mt10 p10">
                <div class="col">
                    <input
                        class="search-field"
                        type="text"
                        id="deskripsi"
                        placeholder="Tambah deskripsi..."
                    />
                </div>
                <div class="col flex">
                    <button class="bt-blue">Filter</button>
                </div>
            </div>
            <div class="mt50">
                <table>
                    <thead>
                        <tr>
                            <th>PRODUCT CODE</th>
                            <th>PRODUCT NAME</th>
                            <th>PRICE</th>
                            <th>STATUS</th>
                            <th>PRODUCT CATEGORY</th>
                            <th>UNIT</th>
                            <th>PRODUCT STATUS</th>
                            <th>PRODUCT IMAGE</th>
                            <th>ACTION</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for="item of list_product" :key="item.id">
                            <td class="center">{{ item.productC }}</td>
                            <td class="center">{{ item.productN }}</td>
                            <td class="center">{{ item.price }}</td>
                            <td class="center">
                                <div v-if="item.status === 1">
                                    <label class="label-green">Publish</label>
                                </div>
                                <div v-if="item.status === 2">
                                    <label class="label-red">Private</label>
                                </div>
                                <td class="center">{{ item.productCt }}</td>
                                <td class="center">{{ item.unit }}</td>
                            </td>
                            <td class="center">
                                <div v-if="item.productS === 1">
                                    <label class="label-green">Availability</label>
                                </div>
                                <div v-if="item.productS === 2">
                                    <label class="label-red">Sold</label>
                                </div>
                            </td>
                            <td class="center">
                                <div>
                                <img :src="require(`../../assets/images/${item.productI}`)" width="65" alt="Nama Gambar" />
                                </div>
                            </td>
                            <td class="center">
                                <div class="mt5">
                                    <router-link :to="`/edit-product/${item.id}`">
                                        <img src="../../assets/icons/edit.svg">
                                    </router-link>
                                </div>
                                <div class="mt5">
                                    <router-link :to="`/detail-product/${item.id}`">
                                        <img src="../../assets/icons/detail.svg">
                                    </router-link>
                                </div>
                                <div class="mt5">
                                    <img src="../../assets/icons/delete.svg">
                                </div>
                            </td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>
</template>

<script>
import Menu from "../../components/menu.vue"

export default {
	name: 'list-product',
	components: {
		Menu
	},
    data(){
        return {
            list_product: [
                {
                    id: "1",
                    productC: "j4f7ewf36",
                    productN: "iPhone 15 128GB",
                    price: "Rp 15.000.000",
                    status: 1,
                    productCt: "Electronic",
                    unit: "20",
                    productS: 1,
                    productI : "iphone15.png",
                },
                {
                    id: "2",
                    productC: "dayx632b1",
                    productN: "iPhone 14 128GB",
                    price: "Rp 12.500.000",
                    status: 1,
                    productCt: "Electronic",
                    unit: "17",
                    productS: 2,
                    productI : "iPhone14.png"
                }
            ]
        }
    }
}
</script>