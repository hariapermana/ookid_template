<template>
  <div class="col-sm-6 col-lg-3">
    <div class="menu-6-item bg-white">
      <span
        class="text-success added-to-cart"
        v-if="cart[product_list_item.slack] != null"
        ><i class="fas fa-check"></i> {{ $t("Added to cart") }}</span
      >
      <!-- IMAGE -->
      <div class="menu-6-img rel">
        <div class="hover-overlay">
          <!-- Image -->
          <img
            :src="
              product_list_item.images.length > 0
                ? product_list_item.images[0].thumbnail
                : '#'
            "
            alt=""
            class="img-fluid"
          />

          <!-- Item Code -->
          <span class="item-code bg-tra-dark">10 pcs</span>

          <!-- Zoom Icon -->
          <div class="menu-img-zoom ico-25">
            <a href="images/produk-1.png" class="image-link">
              <span class="flaticon-zoom"></span>
            </a>
          </div>
        </div>
      </div>

      <!-- TEXT -->
      <div class="menu-6-txt rel">
        <!-- Title -->
        <a
          :href="
            '/our_menu/' +
            store_code +
            '/detail_catalog/' +
            product_list_item.name
          "
          >{{ product_list_item.name | truncate(35) }}</a
        >

        <!-- Description -->
        <p class="grey-color">
          Chicken breast, chilli sauce, tomatoes, pickles, coleslaw
        </p>

        <!-- Price -->
        <div class="menu-6-price bg-coffee">
          <h5 class="h5-xs yellow-color">
            {{ store_currency }}
            {{ product_list_item.sale_amount_excluding_tax }}
          </h5>
        </div>

        <!-- Add To Cart -->
      </div>
    </div>
  </div>
</template>
