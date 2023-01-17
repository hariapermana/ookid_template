<template>
  <div class="card-body">
    <span
      class="text-success added-to-cart"
      v-if="cart[product_list_item.slack] != null"
      ><i class="fas fa-check"></i> {{ $t("Added to cart") }}</span
    >
    <div class="text-break overflow-hidden product-title d-block">
      <a
        :href="
          '/our_menu/' +
          store_code +
          '/detail_catalog/' +
          product_list_item.name
        "
        >{{ product_list_item.name | truncate(35) }}</a
      >
    </div>
    <div class="text-break overflow-hidden d-block">
      <span class="product-price-currency">{{ store_currency }}</span>
      {{ product_list_item.sale_amount_excluding_tax }}
      &nbsp;<span
        v-if="
          product_list_item.discount_code != null &&
          product_list_item.discount_code.discount_percentage > 0
        "
        class="text-success text-caption"
        ><i class="fas fa-tags"></i>
        {{
          product_list_item.discount_code.discount_percentage % 1 == 0
            ? Math.round(product_list_item.discount_code.discount_percentage)
            : product_list_item.discount_code.discount_percentage
        }}%</span
      >
    </div>
    <div class="hide">
      <div class="cart-button d-flex">
        <button
          class="btn btn-info cursor mr-1 w-100"
          v-on:click="modalShare(product_list_item.name)"
        >
          <i class="fas fa-share"></i>
        </button>
        <button
          class="btn btn-primary cursor w-100"
          v-on:click="add_to_cart(product_list_item)"
        >
          <i class="fas fa-shopping-cart"></i>
        </button>
      </div>
    </div>
  </div>
</template>
