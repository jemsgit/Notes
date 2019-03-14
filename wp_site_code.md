Theme: 
	- Neve
Plugins:
	- Force Regenerate Thumbnails - update thumbnails
	- Hide Featured Image
	- Product Gallery Slider for Woocommerce
	- Responsive Lightbox & Gallery
	- WooCommerce
	- WP Mail SMTP
	
- To add "shop" to breadcrumbs -> Settings - Product permalinks - Custom base
 
- Add to cart button on product:
 
	function.php 
 
	function wnc_add_cart_button () {
		add_action( 'woocommerce_after_shop_loop_item_title', 'woocommerce_template_loop_add_to_cart', 10 );
	}

	add_action( 'after_setup_theme', 'wnc_add_cart_button' );
	
- aditional css:

	.woocommerce ul.products li.product .add_to_cart_button {
		width: 100%;
		position: absolute;
		bottom: 60px;
		opacity:0;
	}

	.woocommerce ul.products li.product:hover .add_to_cart_button {
		width: 100%;
		position: absolute;
		bottom: 100px;
		background: white;
		opacity:1;
	}

	.woocommerce ul.products li.product .added_to_cart {
		width: 100%;
		position: absolute;
		bottom: 100px;
		text-align: center;
			color: #515151;
		background: rgba(255,255,255,.8);
		border-radius: 4px;
	}

	@media (max-width: 2200px) and (min-width: 992px) { 
		article #rl-gallery-container-1 .rl-basicgrid-gallery .rl-gallery-item,
		article #rl-gallery-container-2 .rl-basicgrid-gallery .rl-gallery-item,
		article #rl-gallery-container-3 .rl-basicgrid-gallery .rl-gallery-item{
			width: 120px;
			max-height:120px
		}
	}

	@media (min-width: 960px) {
		#content .posts-wrapper article:nth-child(even) .article-content-col .content {
			flex-direction: row-reverse;
		}
	}

	#content .posts-wrapper article:nth-child(even) .article-content-col .content {
		padding-top: 30px;
		padding-left: 20px;
		background-color:rgba(102, 102, 102, 0.35);
	}

	#content .posts-wrapper article:nth-child(even) .article-content-col .content .non-grid-content.default-layout-content {
		padding-left: 0;
		color: white;
	}

	#content article:hover .nv-post-thumbnail-wrap img {
		height: auto;
		filter: contrast(1.2);
	}

	#content .posts-wrapper article:nth-child(even) .article-content-col .content .non-grid-content.default-layout-content a {
		color: white;
	}

	#content .posts-wrapper article:nth-child(even) .article-content-col .content .non-grid-content.default-layout-content .entry-summary {
		color: white;
	}

	#content .posts-wrapper article .article-content-col .content {
		padding-right: 20px;
		padding-top:20px;
	}

	#content .posts-wrapper article {
		margin-bottom: 0;
	}

	.post-products-section {
		  background-color:rgba(0, 0, 0, 0.25);
		padding: 20px 20px 0;
			margin-top: 40px;
	}

	.post-products-section:before {
		content: "Products from series";
		color: white;
		font-size: 20px;
		font-weight: 600;
		text-align: center;
		position: relative;
			display: block;
			margin-bottom: 20px;
	}

	.post-products-section .woocommerce ul.products li.product .price {
		color: white;
		padding: 0;
		line-height: 1em;
	}

	.post-products-section  .woocommerce ul.products li.product .woocommerce-loop-product__title {
		color: white;
		padding: 0;
	}

	.post-products-section
	.woocommerce ul.products li.product a img {
		margin-bottom: 5px;
	}

	.post-products-section
	.woocommerce ul.products li.product:hover .add_to_cart_button {
		bottom: 60px;
	}

	#defaultCanvas0 {
		position: absolute;
		top:0;
		z-index: -1;
	}

	.woocommerce .related.products {
		clear: both;
	}	

	
Links:
 https://docs.bitnami.com/aws/how-to/bitnami-remove-banner/
 https://iconicwp.com/blog/woocommerce-images-blurry-fix/
 https://community.bitnami.com/t/change-default-user-name/62685
 https://atlantisthemes.com/woocommerce-single-product-image/
 
AWS:
	To add key pair View/Change User Data for instance:
	#cloud-config
		ssh_deletekeys: false
		ssh_authorized_keys:
		  - ssh-rsa 'key here'
		cloud_final_modules:
		  - [ssh, always]	