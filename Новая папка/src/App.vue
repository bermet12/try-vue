<template>
  <div>
    <div class="header">
      <div class="container">
        <div class="leftHeader">
          <img src="@/assets/logo.png" alt="" />
        </div>

        <div class="rightHeader">
          <img class="bars" src="@/assets/bars.png" alt="" />
          <img class="userIcon" src="@/assets/user.png" alt="" />

          <span class="cartIconWrap">
            <!-- <img class="cartIcon" src="@/assets/cart.png" alt="" /> -->
            <button class="btn-top" v-on:click="modalOpen"></button>
            <span>0</span>
          </span>
        </div>
      </div>
    </div>

    <div class="modal" v-if="isModalOpen">
      <div class="basketRow basketHeader">
        <div>Название товара</div>
        <div>Количество</div>
        <div>Цена за шт.</div>
        <div>Итого</div>
      </div>
      <div class="basketRow" v-bind:key="index" v-for="(item, index) of cart">
        <div>{{ item.name }}</div>
        <div><span class="productCount" data-productid="1">1</span> шт.</div>
        <div>{{ item.price }}</div>
        <div>
          $<span class="productTotalRow" data-productid="1">{{
            item.price
          }}</span>
        </div>
      </div>
      <div class="basketTotal">
        Товаров в корзине на сумму: $<span class="basketTotalValue">1983</span>
      </div>
    </div>
    <router-view v-bind:catalog="catalog" />
    <div class="newArrivals">
      <div class="container">
        <h1>NEW ARRIVALS</h1>
        <nav>
          <a href="#">HOME</a>
          <span>/</span>
          <a href="#">MEN</a>
          <span>/</span>
          <a href="#">NEW ARRIVALS</a>
        </nav>
      </div>
    </div>
    <div class="catalog_content container_boot">
      <div class="catalog_choice">
        <div class="catalog_search">
          <details class="search_top">
            <summary class="search_txt">
              FILTER
              <img class="catalog_filtr" src="@/assets/filtr.png" alt="filtr" />
            </summary>
            <details class="catalog_menu">
              <summary class="catalog_menu_h3">CATEGORY</summary>
              <a class="menu_a menu_lnk" href="#">Accessories</a>
              <a class="menu_a menu_lnk" href="#">Bags</a>
              <a class="menu_a menu_lnk" href="#">Denim</a>
              <a class="menu_a menu_lnk" href="#">Hoodies &amp; Sweatshirts</a>
              <a class="menu_a menu_lnk" href="#">Jackets &amp; Coats</a>
              <a class="menu_a menu_lnk" href="#">Polos</a>
              <a class="menu_a menu_lnk" href="#">Shirts</a>
              <a class="menu_a menu_lnk" href="#">Shoes</a>
              <a class="menu_a menu_lnk" href="#">Sweaters &amp; Knits</a>
              <a class="menu_a menu_lnk" href="#">T-Shirts</a>
              <a class="menu_a menu_lnk" href="#">Tanks</a>
            </details>
            <details class="catalog_menu">
              <summary class="catalog_menu_h3">BRAND</summary>
              <a class="menu_a menu_lnk" href="#">Accessories</a>
              <a class="menu_a menu_lnk" href="#">Bags</a>
              <a class="menu_a menu_lnk" href="#">Denim</a>
              <a class="menu_a menu_lnk" href="#">Hoodies &amp; Sweatshirts</a>
              <a class="menu_a menu_lnk" href="#">Jackets &amp; Coats</a>
              <a class="menu_a menu_lnk" href="#">Polos</a>
              <a class="menu_a menu_lnk" href="#">Shirts</a>
              <a class="menu_a menu_lnk" href="#">Shoes</a>
              <a class="menu_a menu_lnk" href="#">Sweaters &amp; Knits</a>
              <a class="menu_a menu_lnk" href="#">T-Shirts</a>
              <a class="menu_a menu_lnk" href="#">Tanks</a>
            </details>
            <details class="catalog_menu">
              <summary class="catalog_menu_h3">DESIGNER</summary>
              <a class="menu_a menu_lnk" href="#">Accessories</a>
              <a class="menu_a menu_lnk" href="#">Bags</a>
              <a class="menu_a menu_lnk" href="#">Denim</a>
              <a class="menu_a menu_lnk" href="#">Hoodies &amp; Sweatshirts</a>
              <a class="menu_a menu_lnk" href="#">Jackets &amp; Coats</a>
              <a class="menu_a menu_lnk" href="#">Polos</a>
              <a class="menu_a menu_lnk" href="#">Shirts</a>
              <a class="menu_a menu_lnk" href="#">Shoes</a>
              <a class="menu_a menu_lnk" href="#">Sweaters &amp; Knits</a>
              <a class="menu_a menu_lnk" href="#">T-Shirts</a>
              <a class="menu_a menu_lnk" href="#">Tanks</a>
            </details>
          </details>
          <details class="search_top_dop">
            <summary class="search_txt">
              <img
                class="catalog_filtr"
                src="img/catalog-last-menu.png"
                alt="filtr"
              />
            </summary>
            <details class="catalog_menu">
              <summary class="catalog_menu_h3">CATEGORY</summary>
              <a class="menu_a menu_lnk" href="#">Accessories</a>
              <a class="menu_a menu_lnk" href="#">Bags</a>
              <a class="menu_a menu_lnk" href="#">Denim</a>
              <a class="menu_a menu_lnk" href="#">Hoodies &amp; Sweatshirts</a>
              <a class="menu_a menu_lnk" href="#">Jackets &amp; Coats</a>
              <a class="menu_a menu_lnk" href="#">Polos</a>
              <a class="menu_a menu_lnk" href="#">Shirts</a>
              <a class="menu_a menu_lnk" href="#">Shoes</a>
              <a class="menu_a menu_lnk" href="#">Sweaters &amp; Knits</a>
              <a class="menu_a menu_lnk" href="#">T-Shirts</a>
              <a class="menu_a menu_lnk" href="#">Tanks</a>
            </details>
            <details class="catalog_menu">
              <summary class="catalog_menu_h3">BRAND</summary>
              <a class="menu_a menu_lnk" href="#">Accessories</a>
              <a class="menu_a menu_lnk" href="#">Bags</a>
              <a class="menu_a menu_lnk" href="#">Denim</a>
              <a class="menu_a menu_lnk" href="#">Hoodies &amp; Sweatshirts</a>
              <a class="menu_a menu_lnk" href="#">Jackets &amp; Coats</a>
              <a class="menu_a menu_lnk" href="#">Polos</a>
              <a class="menu_a menu_lnk" href="#">Shirts</a>
              <a class="menu_a menu_lnk" href="#">Shoes</a>
              <a class="menu_a menu_lnk" href="#">Sweaters &amp; Knits</a>
              <a class="menu_a menu_lnk" href="#">T-Shirts</a>
              <a class="menu_a menu_lnk" href="#">Tanks</a>
            </details>
            <details class="catalog_menu">
              <summary class="catalog_menu_h3">DESIGNER</summary>
              <a class="menu_a menu_lnk" href="#">Accessories</a>
              <a class="menu_a menu_lnk" href="#">Bags</a>
              <a class="menu_a menu_lnk" href="#">Denim</a>
              <a class="menu_a menu_lnk" href="#">Hoodies &amp; Sweatshirts</a>
              <a class="menu_a menu_lnk" href="#">Jackets &amp; Coats</a>
              <a class="menu_a menu_lnk" href="#">Polos</a>
              <a class="menu_a menu_lnk" href="#">Shirts</a>
              <a class="menu_a menu_lnk" href="#">Shoes</a>
              <a class="menu_a menu_lnk" href="#">Sweaters &amp; Knits</a>
              <a class="menu_a menu_lnk" href="#">T-Shirts</a>
              <a class="menu_a menu_lnk" href="#">Tanks</a>
            </details>
          </details>
        </div>
        <div class="drop_list catalog_drop_list">
          <select class="dropdown">
            <option class="dropdown-toggl">TRENDING NOW</option>
            <option class="dropdown-toggl">BLACK</option>
            <option class="dropdown-toggl">WHITE</option>
            <option class="dropdown-toggl">RED</option>
            <option class="dropdown-toggl">GREEN</option>
          </select>
          <select class="dropdown">
            <option class="dropdown-toggl">SIZE</option>
            <option class="dropdown-toggl">XS</option>
            <option class="dropdown-toggl">S</option>
            <option class="dropdown-toggl">M</option>
            <option class="dropdown-toggl">L</option>
          </select>
          <select class="dropdown">
            <option class="dropdown-toggl">PRICE</option>
            <option class="dropdown-toggl">1</option>
            <option class="dropdown-toggl">2</option>
            <option class="dropdown-toggl">3</option>
            <option class="dropdown-toggl">4</option>
          </select>
        </div>
      </div>
      <div class="catalog-card">
        <section class="card-box catalog"></section>
        <div>
          <router-link to="/cart">Cart</router-link>
        </div>
      </div>
    </div>
    <footer>
      <div class="footer_top">
        <div class="footer_box container_boot">
          <ul class="footer_ul">
            <li class="footer_card_li">
              <a href="#" class="footer_a">
                <img src="@/assets/car.png" alt="car" /><br />
                <p class="footer_title">Free Delivery</p>
                <br />
                <p class="card_text">
                  Worldwide delivery on all. Authorit tively morph
                  next-generation innov tion with extensive models.
                </p>
              </a>
            </li>
            <li class="footer_card_li dop">
              <a href="#" class="footer_a">
                <img src="@/assets/sale.png" alt="sale" /><br />
                <p class="footer_title">Free Delivery</p>
                <br />
                <p class="card_text">
                  Worldwide delivery on all. Authorit tively morph
                  next-generation innov tion with extensive models.
                </p>
              </a>
            </li>
            <li class="footer_card_li">
              <a href="#" class="footer_a">
                <img src="@/assets/quality.png" alt="quality" /><br />
                <p class="footer_title">Free Delivery</p>
                <br />
                <p class="card_text">
                  Worldwide delivery on all. Authorit tively morph
                  next-generation innov tion with extensive models.
                </p>
              </a>
            </li>
          </ul>
        </div>
      </div>
      <div class="footer_bottom">
        <div class="bottom_box container_boot">
          <div class="footer_mention">
            <figure>
              <img
                class="custom_mention"
                src="@/assets/footer-girl.png"
                alt="customer_feedback"
              />
              <figcaption>
                “Vestibulum quis porttitor dui! Quisque viverra nunc mi, a
                pulvinar purus condimentum“
              </figcaption>
            </figure>
          </div>
          <div class="subscribe">
            <p class="subscribe_text">
              SUBSCRIBE <br />
              <span class="subscribe_span"
                >FOR OUR NEWLETTER AND PROMOTION</span
              >
            </p>
            <form action="#">
              <div class="footer_form">
                <p class="input-text">
                  <input
                    class="footer_input"
                    type="email"
                    placeholder="Enter Your Email"
                  />
                </p>
                <p class="footer_button">
                  <input
                    class="button_subscribe"
                    type="submit"
                    value="Subscribe"
                  />
                </p>
              </div>
            </form>
          </div>
        </div>
        <div class="footer_copy">
          <div class="wrap_copy container_boot">
            <p class="footer_copy_text">© 2021 Brand All Rights Reserved.</p>
            <div class="social_networks">
              <div class="footer_social">
                <a href="#">
                  <i class="fab fa-facebook-f" aria-hidden="true"></i>
                </a>
              </div>
              <div class="footer_social">
                <a href="#">
                  <i class="fab fa-instagram" aria-hidden="true"></i>
                </a>
              </div>
              <div class="footer_social">
                <a href="#">
                  <i class="fab fa-pinterest-p" aria-hidden="true"></i>
                </a>
              </div>
              <div class="footer_social">
                <a href="#">
                  <i class="fab fa-twitter" aria-hidden="true"></i>
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isModalOpen: false,
      cart: [
        { name: "Hat red", price: 657 },
        { name: "Shirt red", price: 382 },
        { name: "Hat black", price: 944 },
      ],
      catalog: [
        {
          id: 1,
          image: "@/assets/card-1.png",
          title: "ELLERY X M'O CAPSULE",
          text: "Known for her sculptural takes on traditional tailoring,Australian arbiter of cool Kym Ellery teams up with Moda Operandi.",
          price: 52.0,
        },
      ],
    };
  },
  methods: {
    modalOpen() {
      return (this.isModalOpen = this.isModalOpen === true ? false : true);
    },
  },
};
</script>
<style lang="scss">
* {
  margin: 0;
  padding: 0;
}
body {
  margin: 0;
  font-family: Lato, sans-serif;
}
.img_1 {
  display: block;
  width: 100%;
}
.catalog-card {
  text-align: center;
}
.btn-top {
  background: url(@/assets/cart.png);
  background-repeat: no-repeat;
  border: 0;
  padding: 27px 18px 2px 24px;
}
.container {
  margin: 0 auto;
  width: 1140px;
}
.header .container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.header {
  background: #222;
  height: 74px;
  padding: 18px 16px;
  box-sizing: border-box;
  display: flex;
  justify-content: flex-end;
  // padding-right: calc(41% - 400px);
}
.rightHeader {
  position: relative;
}
.cartIconWrap {
  position: relative;
  cursor: pointer;
}
.cartIconWrap span {
  display: inline-block;
  width: 19px;
  height: 19px;
  color: white;
  background: #f16d7f;
  border-radius: 50%;
  position: absolute;
  text-align: center;
  right: -8px;
  top: -19px;
  font-size: 12px;
  line-height: 19px;
}
.userIcon {
  margin-left: 25px;
  margin-right: 18px;
}
.basketRow {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
  margin-bottom: 10px;
  border-bottom: 1px solid #ebebeb;
  padding-bottom: 10px;
}
.modal {
  width: 500px;
  font-size: 16px;
  position: absolute;
  right: 160px;
  top: 70px;
  background: white;
  padding: 10px;
  border: 1px solid #ebebeb;
  border-radius: 3px;
}
.basketRow {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
  margin-bottom: 10px;
  border-bottom: 1px solid #ebebeb;
  padding-bottom: 10px;
}
.basketTotal {
  font-weight: bold;
  text-align: right;
}
.container {
  margin: 0 auto;
  width: 1140px;
}
.featured h1 {
  margin-top: 50px;
  margin-bottom: 35px;
  text-align: center;
  color: #222;
}
.newArrivals {
  background: #f8f3f4;
  min-height: 148px;
}
.newArrivals .container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  // flex-direction: column;
  align-items: center;
  min-height: inherit;
}
.newArrivals h1 {
  margin: 24px 0 32px;
  font-weight: normal;
  font-size: 24px;
  line-height: 29px;
  color: #f16d7f;
}
nav {
  display: block;
}
.newArrivals nav a {
  text-decoration: none;
}

.newArrivals nav a,
.newArrivals nav span {
  font-weight: 300;
  font-size: 14px;
  line-height: 17px;
  color: #636363;
}
.newArrivals nav a:last-of-type {
  font-weight: bold;
  color: #f16d7f;
}
.newArrivals nav span {
  margin: 0 3px;
}
.container_boot {
  max-width: 1140px;
  margin: 0 auto;
}
.catalog_content .catalog_choice {
  width: 40%;
  position: absolute;
  display: flex;
  justify-content: space-between;
  margin-top: -100px;
  margin-bottom: 64px;
  z-index: 1;
}
.catalog_content .catalog_choice .catalog_search {
  width: 48%;
  display: flex;
  box-sizing: border-box;
}
.catalog_content .catalog_choice .catalog_search .search_top[open] {
  box-shadow: 6px 4px 35px rgb(0 0 0 / 21%);
  width: 100%;
  flex-direction: column;
  padding-left: 22px;
  z-index: 1;
  background: #ffffff;
  padding-bottom: 16px;
}
.catalog_content .catalog_choice .catalog_search .search_txt {
  display: inline-block;
  font-weight: 600;
  font-size: 14px;
  line-height: 17px;
  color: #000000;
  margin-right: 11px;
}
summary {
  list-style-type: none;
}
.catalog_content .catalog_choice .catalog_search .catalog_filtr {
  width: 15px;
  height: 100%;
  vertical-align: baseline;
  margin-left: 11px;
}
.catalog_content .catalog_choice .catalog_search .catalog_menu_h3 {
  font-size: 14px;
  line-height: 17px;
  color: #ef5b70;
  padding-bottom: 11px;
  margin-top: 24px;
  border-left: 5px solid #ef5b70;
  border-bottom: 1px solid #ebebeb;
  padding-top: 10px;
  padding-left: 11px;
  margin-right: 30px;
}
.catalog_content .catalog_choice .catalog_search .menu_lnk {
  margin-top: 11px;
}
.search_top_dop {
  display: none;
}
.menu_a {
  display: block;
  font-size: 14px;
  line-height: 17px;
  color: #6f6e6e;
  text-decoration: none;
  margin-bottom: 11px;
}
.catalog_content .catalog_choice .catalog_search .search_txt {
  display: inline-block;
  font-weight: 600;
  font-size: 14px;
  line-height: 17px;
  color: #000000;
  margin-right: 11px;
}
.catalog_content .catalog_choice .catalog_search .catalog_filtr {
  width: 15px;
  height: 100%;
  vertical-align: baseline;
  margin-left: 11px;
}
.catalog_content .catalog_choice .catalog_search .search_top[open] .search_txt {
  color: #f16d7f;
  margin-top: 13px;
  margin-left: -16px;
}
.filtersRight {
  display: flex;
  font-size: 12px;
  line-height: 14px;
  color: #6f6e6e;
}
.catalog_drop_list {
  align-items: baseline;
}

.drop_list {
  display: flex;
  justify-content: space-between;
  width: 48%;
}
.drop_list .dropdown {
  display: block;
}

.dropdown,
.dropend,
.dropstart,
.dropup {
  position: relative;
}
select {
  border: none;
  font-size: 14px;
  line-height: 17px;
  color: #6f6e6e;
}
select {
  word-wrap: normal;
}
button,
select {
  text-transform: none;
}
button,
input,
optgroup,
select,
textarea {
  margin: 0;
  font-family: inherit;
}
.drop_list .dropdown .dropdown-toggl {
  display: flex;
  align-items: baseline;
  text-decoration: none;
  font-size: 14px;
  line-height: 17px;
  color: #6f6e6e;
  position: relative;
}
.catalog-card {
  margin-top: 150px;
}
.catalog {
  margin-top: 0;
}

.card-box {
  margin-top: 48px;
  text-align: start;
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  align-items: center;
}
.card-box .card_li {
  max-width: 31.5%;
  background: #f8f8f8;
  margin-bottom: 30px;
  position: relative;
}
.card-box .card_li .card_a {
  display: block;
  text-decoration: none;
  display: flex;
  flex-direction: column;
}
.card-box .card_li .card_a .content_img {
  width: 100%;
}

.card-box .card_li .card_a .card_txt {
  margin: 25px auto 18px 18px;
}
.card-box .card_li .card_a .card_title {
  font-size: 16px;
  line-height: 19px;
  font-weight: 600;
  color: #000000;
  margin-bottom: 13px;
}

p {
  margin-top: 0;
  margin-bottom: 1rem;
}
.card-box .card_li .card_a .card_text {
  font-weight: 300;
  font-size: 14px;
  line-height: 17px;
  color: #5d5d5d;
  margin-bottom: 13px;
}
.card-box .card_li .card_a .card_price {
  font-size: 16px;
  line-height: 19px;
  color: #f16d7f;
  text-decoration: none;
}
.card-box .card_li .add_box {
  display: none;
  position: absolute;
  top: 188.5px;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  width: 100%;
}
.card-box .card_li .add_box .add {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  text-decoration: none;
  color: #ffffff;
  padding: 10px;
  border: 1px solid #ffffff;
}
.card-box .card_li {
  max-width: 31.5%;
  background: #f8f8f8;
  margin-bottom: 30px;
  position: relative;
}
.card-box .card_li .add_box {
  display: none;
  position: absolute;
  top: 188.5px;
  justify-content: center;
  width: 100%;
}
ol,
ul {
  padding-left: 0;
}

dl,
ol,
ul {
  margin-bottom: 0;
}
ul {
  list-style-type: none;
}
.card-box .card_li {
  max-width: 31.5%;
  background: #f8f8f8;
  margin-bottom: 30px;
  position: relative;
}
.footer_top {
  background: #222224;
  margin-top: 95.5px;
  padding-top: 103px;
  padding-bottom: 104px;
}
.container_boot {
  max-width: 1140px;
  margin: 0 auto;
}
.footer_top .footer_ul {
  list-style: none;
  text-align: center;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}
.footer_top .footer_ul .footer_card_li {
  min-height: 134px;
  max-width: 31.5%;
}
.footer_top .footer_ul .footer_card_li .footer_a {
  display: block;
  padding-top: 16px;
  text-decoration: none;
}
.footer_top .footer_ul .footer_card_li .footer_a .footer_title {
  font-size: 19.96px;
  line-height: 24px;
  color: #fbfbfb;
  display: inline-block;
  margin-bottom: 16px;
  margin-top: 28px;
}
.footer_top .footer_ul .footer_card_li .footer_a .card_text {
  font-weight: 300;
  font-size: 14px;
  line-height: 17px;
  color: #5d5d5d;
  margin-bottom: 13px;
}
.footer_top .footer_ul .dop {
  margin-top: -8px;
}
.footer_bottom {
  // background-image: url(img/footer-back.png);
  background-repeat: no-repeat;
  background-size: cover;
  background-position: bottom;
}
.footer_bottom .bottom_box {
  display: flex;
  justify-content: space-between;
}

.container_boot {
  max-width: 1140px;
  margin: 0 auto;
}
.footer_bottom .bottom_box .footer_mention {
  max-width: 327px;
  padding-top: 97px;
  padding-bottom: 211px;
  text-align: center;
}
figure {
  margin: 0 0 1rem;
}
.footer_bottom .bottom_box .subscribe {
  margin-top: 150px;
}
.footer_bottom .bottom_box .subscribe .subscribe_text {
  font-weight: bold;
  font-size: 24px;
  line-height: 167.2%;
  text-align: center;
  color: #222224;
}
.footer_bottom .bottom_box .subscribe .subscribe_text .subscribe_span {
  font-weight: normal;
  font-size: 18px;
  line-height: 30px;
  text-align: center;
  color: #222224;
}
.footer_bottom .bottom_box .subscribe .footer_form {
  display: flex;
  justify-content: center;
  margin-top: 32px;
}
.footer_bottom .bottom_box .subscribe .footer_form .input-text {
  font-size: 14px;
  line-height: 17px;
  align-items: center;
  color: #222224;
}

.footer_bottom .bottom_box .subscribe .footer_form .input-text .footer_input {
  box-sizing: border-box;
  width: 256px;
  height: 57px;
  padding: 7px 64px 7px 22px;
  border-radius: 30px 0 0 30px;
  background: #e1e1e1;
  border-color: transparent;
}
.footer_bottom .bottom_box .subscribe .footer_form .button_subscribe {
  box-sizing: border-box;
  font-size: 14px;
  line-height: 17px;
  align-items: center;
  text-align: center;
  color: #ffffff;
  background: #f16d7f;
  border-radius: 0 30px 30px 0;
  width: 100px;
  padding: 8px;
  height: 57px;
  border-color: transparent;
  transition: 1s;
}
.footer_bottom .footer_copy {
  padding-top: 30px;
  padding-bottom: 30px;
  background: #222224;
}
.footer_bottom .footer_copy .wrap_copy {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  justify-content: space-between;
}
.footer_bottom .footer_copy .wrap_copy .footer_copy_text {
  font-size: 16px;
  line-height: 19px;
  color: #fbfbfb;
}
.footer_bottom .footer_copy .wrap_copy .social_networks {
  width: 147px;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  justify-content: space-between;
}
.footer_bottom .footer_copy .wrap_copy .social_networks .footer_social {
  width: 32px;
  height: 32px;
  background-color: white;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: 1s;
}
</style>