---
layout: post
title: Adding Approved Vendor Logo to WooCommerce Product Vendors
tags: [Woocommerce, Product Vendors]
categories: ['Woocommerce', 'Product Vendors', 'PHP']
---


Woocommerce and Product Vendors are a great way to build a marketplace on top
of WordPress, however, I think it is missing the ability to display an
approved vendor logo next to the vendors that are selling product which are
approved.


In order to do this, we are going to use User Capability Manager plugin to create
custom capabilities such as approved vendor and assign it to the respective vendors.

After assigning the capability to a user that is managing a specific vendor, we can
check if that vendor is containing a user that is an approved vendor by using the
code below

{% highlight php %}
$vendor_id_no = WC_Product_Vendors_Utils::get_vendor_id_from_product( $post->ID );
$vendor_data = get_term_meta( absint( vendor_id_no ), 'vendor_data', true );

$vendor_term = get_term_by( 'id', $vendor_id, WC_PRODUCT_VENDORS_TAXONOMY );

if ( $vendor_data && $vendor_term ) {
	$vendor_data['term_id'] = $vendor_term->term_id;
	$vendor_data['name'] = $vendor_term->name;
	$vendor_data['slug'] = $vendor_term->slug;
	$vendor_data['term_group'] = $vendor_term->term_group;
	$vendor_data['term_taxonomy_id'] = $vendor_term->term_taxonomy_id;
	$vendor_data['taxonomy'] = $vendor_term->taxonomy;
	$vendor_data['description'] = $vendor_term->description;
	$vendor_data['parent'] = $vendor_term->parent;
	$vendor_data['count'] = $vendor_term->count;
	$vendor_data['admins'] = $vendor_term->admins;
}

$user = new WP_User( $vendor_data['admins'] );

foreach ( $user->roles as $role ) {
  if ( $role == 'lcl_apr_hst') {
	echo '<img style="display:inline-block;" alt="Approved Vendor" title="Approved Vendor" src="IMAGE_LINK_HERE" width="20" height="20">';
	}
};
{% endhighlight %}
