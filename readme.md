# Paid Memberships Pro + Conditional Blocks Pro

Example snippet to register to the pmpro_hasMembershipLevel function with Conditional Blocks Pro Custom PHP logic.

WordPress Blocks can be displayed depending on the current users membership level.

https://www.paidmembershipspro.com/documentation/content-controls/require-membership-function/


## Step 1: Place the snippet.

You should add the snippet to your themes functions.php file or a custom plugin.

``` php
/**
 * Show blocks depending on the current users memebership. This snippet registers pmpro_hasMembershipLevel to be used with Conditional Blocks PHP logic.
 *
 * @param array $allowed_functions
 * @return array $allowed_functions
 */
function custom_add_allowed_function_conditional_blocks( $allowed_functions ) {

	// Add Paid Membership Pro Level condition.
	array_push( $allowed_functions, 'pmpro_hasMembershipLevel' );

	return $allowed_functions;
}
add_filter( 'conditional_blocks_filter_php_logic_functions', 'custom_add_allowed_function_conditional_blocks', 10, 1 );

```

## Step 2: 

Use the function `pmpro_hasMembershipLevel()` with Conditional Blocks Pro. 

1. Select a new block and open the Condition Builder. 
2. Select the PHP logic conditions.
3. Type in the function with your membership level ID or name. e.g `pmpro_hasMembershipLevel(10)` or `pmpro_hasMembershipLevel('Yoga')` 

You can also display a specific block to users who do not have the specificed memembership level by using this symbol **!**. E.g `!pmpro_hasMembershipLevel('Yoga')` will display the block to everyone who do not hold a Yoga memembership.

## Step 3: Save!

That's it! Your selected WordPress block should now only display to those who hold one of the membership levels.
