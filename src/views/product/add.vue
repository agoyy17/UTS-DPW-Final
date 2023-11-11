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
                    <h1 class="m0">Add Product</h1>
                    <p class="mt5 mb20 tc-green">Make your product looking good for customer</p>
                </div>
            </div>
            <hr class="uline-grey">
            <div class="mt50 row">
                <div class="w20">
                    <label class="form-label">Product Image</label>
                </div>
                <div class="w0">
                    <label for="input-file" class="form-select" style="cursor: pointer; display: inline-block; width: 80px; height: 80px; overflow: hidden;">
                    <img src="../../assets/images/add-image.png" alt="Icon Foto" width="32" height="32"> Tambahkan Foto
                    <input type="file" accept="images/" id="input-file" style="opacity: 0; position: absolute; top: 0; left: 0;">
                    </label>
                    </div>
            </div>
            <div class="mt50 row">
                <div class="w20">
                    <label class="form-label">Product Code</label>
                </div>
                <div class="w80">
                    <input
                        class="form-text"
                        type="text"
                        placeholder="Product Code"
                    >
                </div>
            </div>
            <div class="mt30 row">
                <div class="w20">
                    <label class="form-label">Product Name</label>
                </div>
                <div class="w80">
                    <input
                        class="form-text"
                        type="text"
                        placeholder="Product Name"
                        maxlength="20"
                        oninput="updateCharacterCount(this)"
                    >
                </div>
            </div>
            
            <div class="mt30 row">
                <div class="w20">
                    <label class="form-label">Price</label>
                </div>
                <div class="w80">
                    <input
                        class="form-text"
                        type="text"
                        placeholder="Price"
                    >
                </div>
            </div>
            <div class="mt30 row">
                <div class="w20">
                    <label class="form-label">Product Description</label>
                </div>
                    <div class="w80">
                    <textarea
                        class="form-text"
                        type="text"
                        placeholder="Masukkan Product Description"
                    ></textarea>   
                </div>
                
            </div>
            <div class="mt30 row">
                <div class="w20">
                    <label class="form-label">Unit</label>
                </div>
                <div class="w80">
                    <input
                        class="form-text"
                        type="text"
                        placeholder="Unit"
                    >
                </div>
            </div>
            <div class="mt30 row">
                <div class="w20">
                    <label class="form-label">Min Purchase</label>
                </div>
                <div class="w80">
                    <input
                        class="form-text"
                        type="text"
                        placeholder="Min Purchase"
                    >
                </div>
            </div>
            <div class="mt30 row">
                <div class="w20">
                    <label class="form-label">Max Purchase</label>
                </div>
                <div class="w80">
                    <input
                        class="form-text"
                        type="text"
                        placeholder="Max Purchase"
                    >
                </div>
            </div>
            <div class="mt30 row">
                <div class="w20">
                    <label class="form-label">Category</label>
                </div>
                <div class="w80">
                    <input
                        class="form-text"
                        type="text"
                        placeholder="Category"
                    >
                </div>
            </div>
            <div class="flex mt30">
                <router-link to="/list-product">
                    <button class="bt-submit-green">Add Product</button>
                </router-link>
            </div>
        </div>
    </div>
</template>

<script>
export default {
	name: 'add-product'
}
</script>