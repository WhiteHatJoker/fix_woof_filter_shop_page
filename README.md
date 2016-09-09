# Fixing the issue of woof filtering on main shop page - woof filter resukts showing product categories instead of products #
If you have installed WooCommerce Products Filter by realmag777 and set the shop base to display categories in woocommerce settings, you may notice that using woof filters from your main shop page brings products categories instead of filtered products result. This issue can be easily resolved by changing the woocommerce settings back to show all products on the main shop page, but, if you still would like to have product categories on main shop page, you would need to update your archive-product.php file.

## Installation ##
Just copy the archive-product.php to your current theme folder/woocommerce/

## Manual installation if you have different version of archive-product.php or custom code there ##
Instead of the line 67 that was `<?php woocommerce_product_subcategories(); ?>` put :
```php
if ( !strpos($_SERVER['REQUEST_URI'], "swoof")) {
    woocommerce_product_subcategories();
} ?>
```
Note: If you had changed the default search slug "swoof" in WOOF settings->Advanced->Options->Search slug update the code above with your keyword instead of swoof.
