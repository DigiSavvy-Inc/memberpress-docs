# Known Plugin and Theme Conflicts and Incompatibilities | MemberPress

## Additional menu

[](https://memberpress.com/)MemberPress

The All-In-One WordPress Membership Plugin

 

![worker bees](https://memberpress.com/wp-content/themes/memberpress-theme/images/memberpress-logo-color.svg)

				Get MemberPress today! Start getting paid for the content you create!

[Get MemberPress Now](https://memberpress.com/plans/pricing/)

Search For

Search

# Known Plugin and Theme Conflicts and Incompatibilities

MemberPress works great with most of the plugins and themes (though we may not integrate with all of them)!

Below, however, is a list of known plugin and theme conflicts. Please review this list for the plugin or theme you are wondering about.

Contents:

[Themes

Astra
Avada
BuddyBoss
Cargo HUB
Daily Observer
Flatsome
Flynt
Memberoni
Newspaper
ThimPress
Uncode
Zion Page Builder (Kallyas)

Conditional Theme Conflicts

Enfold
Divi
Salient

Not Supported Themes

Kalium
VideoRev

Plugins

404 Redirection
Admin and Site Enhancements (ASE)
All In One WP Security & Firewall
The Bluehost Plugin
Breakdance
BuddyPress
BuddyBoss Platform
Bunny.net+BunnyAPI plugin
Change WP Admin Login
Classic Editor
CoursePress (WPMUdev)
Elementor's Element Caching
Email Protector
Events Manager
Gravity Forms
iThemes Security plugin
Ivory Search
Jetpack
Jetpack Boost
LearnDash
miniOrange 2 Factor Authentication
Perfmatters
Profile Builder
Redis Object Cache
Relevanssi
S3 Media Vault
SeedProd (Pro)
Speed Optimizer
Smush Plugin by WPMU Dev
Stop Spammers
tagDiv Composer Front-End Page Builder
Theme My Login
Upsell
WP Forms Pro
WP Fusion
WPMU DEV Dashboard
WP Rocket
WP Rocket | Enforce Trailing Slash on URLs

Conditional Plugin Conflicts

Asset CleanUp: Page Speed Booster
Curation Suite
Elementor Popups
Post and Page Builder from BoldGrid
Power BI Embedded for WordPress
PushEngage Web Push Notifications
StreamWeasels
Yoast – Open Graph data
WP Links Page

Not Supported Plugins

Complianz GDPR Premium
Constant Contact Forms
Custom Login Page Customizer
Force SSL Everywhere plugin
GP Advanced Phone Field
Invisible ReCAPTCHA
LearnPress – WordPress LMS Plugin
OptimizePress Suite Dashboard
Print Post and Page
Role Scoper
Root Relative URLs
StreamWeasels
White Label CMS
WooCommerce Sync for QuickBooks Online ? by MyWorks Software
WP Limit Login Attempts
WP Multisite SSO
WP Remote Users Sync
WP Stagecoach
Yith WooCommerce Gift Cards](https://memberpress.com#themes)
## Themes

### Astra Theme

MemberPress login form shows up in the header and/or footer of a page. The issue is present in the Astra Free theme version 1.6.0 and newer as well as with the Astra Pro Addon:

### Avada Theme

Course card image does not display on the “My Courses” or “All Courses” page:

Pages with the Registration Form Shortcode don't work:

```
function mepr_custom_product_pages($return, $post) {
     if($post->ID == [PageId]) {
          return new MeprProduct([MembershipId]); 
     }
}
add_filter('mepr-is-product-page', 'mepr_custom_product_pages', 10, 2);
```

### BuddyBoss Theme

Theme overrides translation to a foreign language provided by MemberPress. For instance, the registration form is back in English:

Setting the “Restrict site access to only logged-in members” overrides the MemberPress “Redirect unauthorized visitors to a specific URL” functionality:

Using the BuddyBoss theme with the MemberPress Gifting Add-On causes fatal errors:

The corporate account's “Manage sub-accounts” link does not work:

### Cargo HUB – Transportation and Logistics WordPress Theme

When the theme is active, it will add the “Expires on” column in the MemberPress > Members section, which will occasionally have mangled data:

### Daily Observer Theme

When the theme is active, the Stripe Credit Card form fails to load. This is caused by a custom jQuery script in the theme that runs and attempts to fix iframe z-index values for older IE browsers:

### Flatsome Theme

When used with the ReadyLaunch Pro template, the bottom of the pages show elements that shouldn't be there.

```
.mepr-pro-template #main-menu {
     display: none;
}
.mepr-pro-template .lightbox-content {
     display: none;
}
```

### Flynt Theme

The theme renders the content outside the standard WordPress content area, so MemberPress rules with default settings can't protect it.

### Memberoni Theme

Stripe payments do not complete, and the message “An error occurred, please DO NOT submit the form again as you may be double charged. Please contact us for further assistance instead” pops up upon the registration form submission:

### Newspaper Theme

Stripe payments fail when the tagDiv Composer plugin is activated. Other themes that come with tagDiv Composer bundled may run into the same issue:

If you use custom templates (post templates) created with their tool/plugin “tagdiv Composer” and their “Cloud templates” with custom settings, you'll run into an issue with the MemberPress plugin generating a protected page with excerpt only without a title of a post and styles:

### ThimPress Themes

When a theme developed by ThimPress is active, the registration process will not send users to the payment page but will redirect the user away from the registration process, usually to your home page:

```
function disable_user_register_mepr() {     remove_action('user_register', 'thim_register_extra_fields', 1000);}add_filter('mepr-validate-signup', 'disable_user_register_mepr');
```

### Uncode Theme

The login, account, and membership registration pages are blank:

### Zion Page Builder (Kallyas theme)

Themes like Kallyas, which use Zion Page Builder to build their membership pages, need to make sure the  shortcode is in BOTH the page builder and the regular page content.

## Conditional Theme Conflicts

### Enfold Theme

Note:  This issue is only present when creating courses with the MemberPress Courses addon.

When editing a Lesson or Quiz in MemberPress Courses, the classic editor is displayed instead of the MemberPress Lesson or Quiz editor:

The courses page is not responsive while using Enfold Theme.

```
html.avia_mobile {  min-width: 0px;}
```

### Divi Theme

Note:  This issue is only present when creating courses with the MemberPress Courses addon.

When editing a Lesson or Quiz in MemberPress Courses, the classic editor is displayed instead of the MemberPress Lesson or Quiz editor:

Note:  This issue is only present when creating courses with the MemberPress Courses addon.

When you go to view a course using the link under the course title (“View”), although you see the pages, you can't advance through the course:

### Salient – Responsive Multi-Purpose Theme

When the Enable Fancy Select/Checkbox/Radio Styling option found in this theme's Dashboard > Theme Options > Form Styling is enabled, the geolocation required to auto-populate and fill the default country and state address fields fails.

Note:  This issue is only present when creating courses with the MemberPress Courses addon.

The user is getting a link expired error when trying to use the theme with MemberPress Courses:

## Not Supported Themes

### Kalium Theme

When activated, the Register button doesn't work:

### VideoRev Theme

It's not possible to integrate MemberPress with full functionality in the VideoRev theme. The theme author wasn't able to make it work:

## Plugins

### 404 Redirection

When the 404 Redirection plugin is activated, the tabs on the Account page do not work:

![](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzMDAiIGhlaWdodD0iMjQiPjxnIGZpbHRlcj0iYmx1cigxMnB4KSI+PHJlY3Qgd2lkdGg9IjIwMCUiIGhlaWdodD0iMjAwJSIgeD0iLTUwJSIgeT0iLTUwJSIgZmlsbD0iIzRjNGM0YyIvPjxyZWN0IHdpZHRoPSIxMDAlIiBoZWlnaHQ9IjEwMCUiIGZpbGw9IiM0YzRjNGMiLz48ZyBmaWxsLW9wYWNpdHk9Ii41IiB0cmFuc2Zvcm09InRyYW5zbGF0ZSguNiAuNilzY2FsZSgxLjE3MTg4KSI+PGNpcmNsZSBjeD0iMTI5IiByPSIxNTEiIGZpbGw9IiNmZmYiLz48ZWxsaXBzZSBjeD0iMTE2IiBjeT0iOSIgZmlsbD0iI2ZmZiIgcng9IjE4NSIgcnk9IjI0Ii8+PGNpcmNsZSByPSIxIiBmaWxsPSIjZWRlZGVkIiB0cmFuc2Zvcm09InJvdGF0ZSgxNjguNyA2My42IDE2LjQpc2NhbGUoMTI4LjQxNTY2IDE1Mi44MjA4MikiLz48Y2lyY2xlIGN4PSI3NCIgY3k9IjE0IiByPSIyMiIgZmlsbD0iI2UwZTBlMCIvPjwvZz48L2c+PC9zdmc+)
### Admin and Site Enhancements (ASE)

Enabling the Redirect after login option will initiate redirection on registration as soon as MemberPress creates a user's profile. This prevents the registration process from initiating payment processing and completing.

### All In One WP Security & Firewall

Members cannot log in after registering and logging out if the MemberPress Math CAPTCHA add-on is enabled:

Activating the Enable manual approval of new registrations option in All In One WP Security & Firewall will block member login. As a result, members will not be able to log in, and the “ACCOUNT PENDING” notification will be displayed.

### The Bluehost Plugin

The Bluehost Plugin comes pre-installed on the WordPress websites hosted by Bluehost. The plugin enforces a strong password requirement for all new users. If a user subscribes using a weak password, the plugin will trigger an error at MemberPress checkout. In addition, this will also trigger an email with the error report to be sent to the website admin.

### Breakdance

The course featured image and curriculum are not visible, and the progress bar stops working. These issues are only present if the ReadyLaunch Courses template and the Breakdance page builder are active simultaneously.

### BuddyPress

The WordPress admin bar (toolbar) shows up at the top for all visitors even though it is disabled in the Dashboard > MemberPress > Settings > Account tab:

![](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzMDAiIGhlaWdodD0iMTUwIj48ZyBmaWx0ZXI9ImJsdXIoMTJweCkiPjxyZWN0IHdpZHRoPSIyMDAlIiBoZWlnaHQ9IjIwMCUiIHg9Ii01MCUiIHk9Ii01MCUiIGZpbGw9IiM0YzRjNGMiLz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSIjNGM0YzRjIi8+PGcgZmlsbD0iI2ZmZiIgZmlsbC1vcGFjaXR5PSIuNSIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLjYgLjYpc2NhbGUoMS4xNzE4OCkiPjxjaXJjbGUgY3g9IjE0MiIgY3k9IjcyIiByPSIxNzciLz48Y2lyY2xlIGN4PSIxNTYiIGN5PSI5IiByPSIxOTkiLz48Y2lyY2xlIGN4PSIxNzIiIGN5PSI3MiIgcj0iMjAxIi8+PGNpcmNsZSBjeD0iOTAiIGN5PSI3MCIgcj0iMTkxIi8+PC9nPjwvZz48L3N2Zz4=)
### BuddyBoss Platform

The header does not appear on the registration page:

The WordPress admin bar (toolbar) shows up at the top for all members and visitors even though it is disabled in the Dashboard > MemberPress > Settings > Account tab:

![](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzMDAiIGhlaWdodD0iMTc5Ij48ZyBmaWx0ZXI9ImJsdXIoMTJweCkiPjxyZWN0IHdpZHRoPSIyMDAlIiBoZWlnaHQ9IjIwMCUiIHg9Ii01MCUiIHk9Ii01MCUiIGZpbGw9IiM0YzRjNGMiLz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSIjNGM0YzRjIi8+PGcgZmlsbD0iI2ZmZiIgZmlsbC1vcGFjaXR5PSIuNSIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLjYgLjYpc2NhbGUoMS4xNzE4OCkiPjxjaXJjbGUgY3g9IjE2MSIgY3k9IjYxIiByPSIxOTEiLz48ZWxsaXBzZSBjeD0iMTUwIiBjeT0iODYiIHJ4PSIyMDIiIHJ5PSIxMzIiLz48Y2lyY2xlIHI9IjEiIHRyYW5zZm9ybT0ibWF0cml4KC0yMTAuODA3OTIgMjcuMDA1MTIgLTE2Ljc1ODEgLTEzMC44MTc0OSAxNTUgNzkuMykiLz48Y2lyY2xlIHI9IjEiIHRyYW5zZm9ybT0ibWF0cml4KC0yNTIuMTg2MDkgMzcuNzc4IC0xMC44MDk5IC03Mi4xNjEyIDE2Ny42IDk1LjgpIi8+PC9nPjwvZz48L3N2Zz4=)![](https://memberpress.com/wp-content/uploads/2024/02/file-Qdohrhxi1k.png)
### Bunny.net+BunnyAPI plugin

When enabled, MemberPress's Settings page takes a very long time to load and also looks visually broken:

### Change WP Admin Login

When enabled, an attempt to pay using Stripe Elements fails with an error message, and Stripe Checkout fails to pass transaction details to MemberPress.

### Classic Editor

When editing a Lesson or Quiz in MP Courses, the classic editor is displayed instead of the MemberPress Lesson or Quiz editor:

```
add_filter('classic_editor_enabled_editors_for_post_type', function ($editors, $post_type) { 
     if ($post_type == 'mpcs-course' || $post_type == 'mpcs-lesson' || $post_type = 'mpcs-quiz') { 
          $editors['classic_editor'] = false; 
     } return $editors;
}, 10, 2);
```

### CoursePress (WPMUdev)

### Elementor's Element Caching

Element Caching will create issues when applying partial rules and dripping settings to Elementor widgets, sections, and containers.

### Email Protector

When activated, PayPal Standard will not work:

### Events Manager

When using the Custom phone field, it generates a JS issue while checking out because the Events Manager plugin uses the same phone JS library:

![](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzMDAiIGhlaWdodD0iNjUiPjxnIGZpbHRlcj0iYmx1cigxMnB4KSI+PHJlY3Qgd2lkdGg9IjIwMCUiIGhlaWdodD0iMjAwJSIgeD0iLTUwJSIgeT0iLTUwJSIgZmlsbD0iIzRjNGM0YyIvPjxyZWN0IHdpZHRoPSIxMDAlIiBoZWlnaHQ9IjEwMCUiIGZpbGw9IiM0YzRjNGMiLz48ZyBmaWxsPSIjZmZmIiBmaWxsLW9wYWNpdHk9Ii41IiB0cmFuc2Zvcm09InRyYW5zbGF0ZSguNiAuNilzY2FsZSgxLjE3MTg4KSI+PGNpcmNsZSBjeD0iMTU3IiBjeT0iMjAiIHI9IjE4NCIvPjxlbGxpcHNlIGN4PSIxMzgiIGN5PSIyOSIgcng9IjE5MCIgcnk9IjU1Ii8+PGNpcmNsZSBjeD0iMTMxIiBjeT0iNTEiIHI9IjE0MiIvPjxjaXJjbGUgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoLTI0LjMwNDY5IC0xMDguNzMyOTMgMTgyLjQyMjMgLTQwLjc3NjIxIDE1NC43IDApIi8+PC9nPjwvZz48L3N2Zz4=)![](https://memberpress.com/wp-content/uploads/2024/02/file-md1WnFoJxy.png)
### Gravity Forms

The checkout page shows the “Country is unknown. Try using a 2-character alphanumeric country code instead, such as US, EG or GB. A full list of country codes is available at https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2#Officially_assigned_code_element” error:

### iThemes Security plugin

PayPal Standard return after payment shows a blank page:

Note: Please keep in mind that the “Filter Long URL Strings” option doesn't exist in the plugin version 8.0.0 and later.

The login page shows an “Error: Invalid username, email address or incorrect password.” error:

A customer gets this message when trying to pay through Stripe: “An error occurred, please DO NOT submit the form again as you might be double charged. Please contact us for further assistance instead.“. The cause of this error is the Enforce Strong Passwords option in iThemes Security while a customer is using a “weak” password. There are several ways to handle this, you can pick the one you like best:

![](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzMDAiIGhlaWdodD0iNDMiPjxnIGZpbHRlcj0iYmx1cigxMnB4KSI+PHJlY3Qgd2lkdGg9IjIwMCUiIGhlaWdodD0iMjAwJSIgeD0iLTUwJSIgeT0iLTUwJSIgZmlsbD0iIzRjNGM0YyIvPjxyZWN0IHdpZHRoPSIxMDAlIiBoZWlnaHQ9IjEwMCUiIGZpbGw9IiM0YzRjNGMiLz48ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSguNiAuNilzY2FsZSgxLjE3MTg4KSI+PGNpcmNsZSBjeD0iMTUwIiBjeT0iMjAiIHI9IjE2NSIgZmlsbD0iI2ZmZiIgZmlsbC1vcGFjaXR5PSIuNSIvPjxjaXJjbGUgcj0iMSIgZmlsbD0iI2ZmZiIgZmlsbC1vcGFjaXR5PSIuNSIgdHJhbnNmb3JtPSJtYXRyaXgoMTUwLjAyMTE4IDIxLjYxODM4IC0xNC4xODg0IDk4LjQ2MDY1IDEyMS41IDIuNCkiLz48Y2lyY2xlIHI9IjEiIGZpbGw9IiNlZGVkZWQiIGZpbGwtb3BhY2l0eT0iLjUiIHRyYW5zZm9ybT0ibWF0cml4KDE1LjU1NzI5IDcyLjM1MzgyIC0xNTIuODAyOTcgMzIuODU1MjEgMTQwLjIgOCkiLz48cGF0aCBmaWxsPSJub25lIiBzdHJva2U9IiNlMGUwZTAiIHN0cm9rZS1vcGFjaXR5PSIuNSIgc3Ryb2tlLXdpZHRoPSIuNSIgZD0iTTgyLjUgMjkuMVE4OC4zIDUuMiA2NS4xIDAiLz48L2c+PC9nPjwvc3ZnPg==)![](https://memberpress.com/wp-content/uploads/2024/02/file-Jn5sv8CVHZ.png)
Note: Please keep in mind that there might be a discrepancy between the MemberPress assessment of a “strong password” and the assessment done by iThemes Security.

### Ivory Search

When activated, when the search includes MemberPress Courses, the search results are not properly displayed:

### Jetpack

The login page shows a math CAPTCHA that can never be solved:

After logging in through the MemberPress login page, a user gets redirected to the WordPress login page.

![](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzMDAiIGhlaWdodD0iNzUiPjxnIGZpbHRlcj0iYmx1cigxMnB4KSI+PHJlY3Qgd2lkdGg9IjIwMCUiIGhlaWdodD0iMjAwJSIgeD0iLTUwJSIgeT0iLTUwJSIgZmlsbD0ibXV0ZWQiLz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIi8+PGcgZmlsbD0iI2ZmZiIgZmlsbC1vcGFjaXR5PSIuNSIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLjYgLjYpc2NhbGUoMS4xNzE4OCkiPjxjaXJjbGUgY3g9IjEyNiIgY3k9IjMxIiByPSIxNDEiLz48Y2lyY2xlIGN4PSIxMTYiIGN5PSIxOCIgcj0iMTQ5Ii8+PGNpcmNsZSBjeD0iMTE0IiBjeT0iMjYiIHI9IjE2MiIvPjxjaXJjbGUgY3g9IjEyMyIgY3k9IjMwIiByPSIxNDIiLz48L2c+PC9nPjwvc3ZnPg==)![](https://memberpress.com/wp-content/uploads/2024/02/file-tF7GPeZtph.png)
Also, if this doesn't help, you'll need to disable the Brute force protection too:

![](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzMDAiIGhlaWdodD0iOTgiPjxnIGZpbHRlcj0iYmx1cigxMnB4KSI+PHJlY3Qgd2lkdGg9IjIwMCUiIGhlaWdodD0iMjAwJSIgeD0iLTUwJSIgeT0iLTUwJSIgZmlsbD0ibXV0ZWQiLz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIi8+PGcgZmlsbD0iI2ZmZiIgZmlsbC1vcGFjaXR5PSIuNSIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLjYgLjYpc2NhbGUoMS4xNzE4OCkiPjxjaXJjbGUgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoLTIuMzgyNyAtOTcuNDkzNzUgMjI2LjE1NzUyIC01LjUyNzE3IDk2LjYgNDIuNCkiLz48Y2lyY2xlIGN4PSIxMzciIGN5PSI0MCIgcj0iMTYzIi8+PGNpcmNsZSBjeD0iMTA1IiBjeT0iMzAiIHI9IjE2MiIvPjxjaXJjbGUgY3g9IjEzNCIgY3k9IjUxIiByPSIxNDgiLz48L2c+PC9nPjwvc3ZnPg==)![](https://memberpress.com/wp-content/uploads/2024/02/file-pg8JzMmZKB.png)

Images and videos are not visible in MemberPress Courses.

![](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzMDAiIGhlaWdodD0iNDQiPjxnIGZpbHRlcj0iYmx1cigxMnB4KSI+PHJlY3Qgd2lkdGg9IjIwMCUiIGhlaWdodD0iMjAwJSIgeD0iLTUwJSIgeT0iLTUwJSIgZmlsbD0ibXV0ZWQiLz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIi8+PGcgZmlsbD0iI2ZmZiIgZmlsbC1vcGFjaXR5PSIuNSIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLjYgLjYpc2NhbGUoMS4xNzE4OCkiPjxjaXJjbGUgY3g9IjEzNiIgY3k9IjIwIiByPSIxNDMiLz48Y2lyY2xlIGN4PSIxMjQiIGN5PSIyMSIgcj0iMTM0Ii8+PGNpcmNsZSBjeD0iMTU1IiBjeT0iMzEiIHI9IjE2NCIvPjxjaXJjbGUgY3g9IjE0NCIgY3k9IjE3IiByPSIxNjYiLz48L2c+PC9nPjwvc3ZnPg==)![](https://memberpress.com/wp-content/uploads/2024/02/file-eJDGNwLUgi.png)

Embedded videos cover the text underneath them when added to MemberPress courses:

![](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzMDAiIGhlaWdodD0iMjIiPjxnIGZpbHRlcj0iYmx1cigxMnB4KSI+PHJlY3Qgd2lkdGg9IjIwMCUiIGhlaWdodD0iMjAwJSIgeD0iLTUwJSIgeT0iLTUwJSIgZmlsbD0ibXV0ZWQiLz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIi8+PGcgZmlsbD0iI2ZmZiIgZmlsbC1vcGFjaXR5PSIuNSIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLjYgLjYpc2NhbGUoMS4xNzE4OCkiPjxjaXJjbGUgY3g9IjEzNiIgY3k9IjEyIiByPSIxNTEiLz48Y2lyY2xlIGN4PSIxNDMiIGN5PSIxMCIgcj0iMTQ3Ii8+PGNpcmNsZSBjeD0iMTE4IiBjeT0iMTEiIHI9IjE0MiIvPjxjaXJjbGUgY3g9IjE2MCIgcj0iMTY4Ii8+PC9nPjwvZz48L3N2Zz4=)![](https://memberpress.com/wp-content/uploads/2024/02/file-31do2Ulfki.png)

When the Gutenberg “YouTube” block is used in a Course, and the “Resize for smaller devices” option is enabled, the video will not be displayed on the front end of the Course.

### Jetpack Boost

Some files downloaded using the MemberPress Downloads add-on are empty:

### LearnDash

LearnDash Courses not being added when a membership is purchased:

```
add_filter('learndash_memberpress_min_courses_count_for_silent_course_enrollment', function( $count ) { 
     return 999; // Big number so it won't use background course enrollment
});
```

### miniOrange 2 Factor Authentication

Registration and checkout don't work, especially with Stripe. You may receive several email messages from MemberPress saying that there was an error during checkout. Also, if you test, you will notice that the first time you click the sign-up button, it doesn't work, but if you click it again, it works fine:

```
function mepr_disable_auto_login($auto_login, $membership_id, $mepr_user) {
     return false;
} 
add_filter('mepr-auto-login', 'mepr_disable_auto_login', 10, 3);
```

### Perfmatters

The course card image is not visible on the “My Courses” or “All Courses” pages:

### Profile Builder

Membership subscribers are not able to log in and get the “Your Account has to be confirmed by an administrator before you can log in” error:

### Redis Object Cache

Causes various problems with MemberPress functionality, due to object caching:

### Relevanssi and Relevanssi Premium

When installed and active, search results don't show any protected posts.

```
add_action('init', function () {
     remove_filter('relevanssi_post_ok', 'relevanssi_memberpress_compatibility');
}, 20);
```

### S3 Media Vault

Videos inserted into MP Courses and lessons with the S3 Media Vault shortcode display a blank screen playing them.

```
add_filter('mpcs_classroom_style_handles', function( $allowed_handles ) {
     $allowed_handles[] = 'vjscss'; 
     $allowed_handles[] = 'ccpsacss'; 
     return $allowed_handles;
});
```

### SeedProd (Pro)

This plugin causes MemberPress' Login page to redirect to the homepage, thus making it impossible to set it up or test the login process during development:

![](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzMDAiIGhlaWdodD0iMTgyIj48ZyBmaWx0ZXI9ImJsdXIoMTJweCkiPjxyZWN0IHdpZHRoPSIyMDAlIiBoZWlnaHQ9IjIwMCUiIHg9Ii01MCUiIHk9Ii01MCUiIGZpbGw9IiM0YzRjNGMiLz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSIjNGM0YzRjIi8+PGcgZmlsbD0iI2ZmZiIgZmlsbC1vcGFjaXR5PSIuNSIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLjYgLjYpc2NhbGUoMS4xNzE4OCkiPjxjaXJjbGUgY3g9IjEyMCIgY3k9Ijc3IiByPSIxNzEiLz48Y2lyY2xlIGN4PSIxMzAiIGN5PSI4NSIgcj0iMTYwIi8+PGNpcmNsZSByPSIxIiB0cmFuc2Zvcm09Im1hdHJpeCgxNzIuNTkwNjkgMTEuNTAxMDcgLTkuNDUwODMgMTQxLjgyMzc2IDEzOS40IDc0KSIvPjxjaXJjbGUgcj0iMSIgdHJhbnNmb3JtPSJyb3RhdGUoMTAgLTM2Ni4xIDk0MylzY2FsZSgxNzUuMTIxOTcgMTAzLjA0MDIzKSIvPjwvZz48L2c+PC9zdmc+)
Though the explanation says that you could use a URL, it does not work for MemberPress.

Searching through the WordPress Search Widget will result in having you redirected to the page set up as the unauthorized redirect page in MemberPress:

### Speed-Optimizer (previously SG Optimizer)

Embedded videos do not appear in Courses:

### Smush Plugin by WPMU Dev

Embedded videos show in preview page mode but not on the actual:

### Stop Spammers

Stripe recurring subscriptions may fail because transaction data never reaches MemberPress due to the Stop Spammers plugin interfering with Webhook functionality. It is to be expected that the same interference would happen with PayPal and Authorize.net, though we don't have confirmation of that at the moment.

### tagDiv Composer Front-End Page Builder

Causes Stripe payments to fail. Hooks into wp_head with an anonymous function, and the event listeners added in through that hook will break promises in JavaScript. This will break certain parts of MemberPress that rely on promises, such as Stripe:

### Theme My Login

Alters the logout URL breaking the MemberPress logout functionality:

### Upsell

Note: This issue is related to the core Upsell plugin, and not the Upsell – MemberPress addon.

When using ReadyLaunch(tm) on the Account page, the “Subscription” option in the navigation will have a blank label:

### WP Forms Pro

The Custom Phone Number Field is not working on the Account or Registration field:

### WP Fusion

When used with Elementor and the MemberPress Elementor Content Protection add-on, WP Fusion causes MemberPress rule settings in Elementor to be ignored. This is because the WP Fusion code runs after the MemberPress Code:

```
add_filter('elementor/frontend/section/should_render', 'mepr_cust_should_render', 10, 999 );

function mepr_cust_should_render($should_render, $element) {
     $mp_elementor = new \MpElementor();
     return $mp_elementor->should_render($should_render, $element);
}
```

### WPMU DEV Dashboard

When enabled, Cron Jobs, especially the MemberPress Cron Jobs, do not run properly:

### WP Rocket

Images and videos do not appear in MemberPress Courses.

![](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzMDAiIGhlaWdodD0iMjQ2Ij48ZyBmaWx0ZXI9ImJsdXIoMTJweCkiPjxyZWN0IHdpZHRoPSIyMDAlIiBoZWlnaHQ9IjIwMCUiIHg9Ii01MCUiIHk9Ii01MCUiIGZpbGw9IiM4NDg0ODQiLz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSIjODQ4NDg0Ii8+PGcgZmlsbC1vcGFjaXR5PSIuNSIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLjYgLjYpc2NhbGUoMS4xNzE4OCkiPjxjaXJjbGUgcj0iMSIgZmlsbD0iI2ZmZiIgdHJhbnNmb3JtPSJyb3RhdGUoLTg5LjYgMTM3LjMgLTMxLjQpc2NhbGUoMjU1IDExOS4yOTYwNSkiLz48Y2lyY2xlIHI9IjEiIGZpbGw9IiNmZmYiIHRyYW5zZm9ybT0ibWF0cml4KDEwNi43NDgzIC45MzE1OCAtMi4wNzMwNSAyMzcuNTQ3ODMgMTc5IDEwOCkiLz48ZWxsaXBzZSBjeD0iMTIiIGN5PSI5MyIgZmlsbD0iIzE3MTcxNyIgcng9IjI0IiByeT0iMjA5Ii8+PGNpcmNsZSByPSIxIiBmaWxsPSIjZmZmIiB0cmFuc2Zvcm09InJvdGF0ZSgxNC40IC0zMDcuMyA4MzkuMylzY2FsZSg5OS4wNTY1OCAxNTAuMTQyNTIpIi8+PC9nPjwvZz48L3N2Zz4=)![](https://memberpress.com/wp-content/uploads/2024/02/file-D42rvxCi9k.png)
### WP Rocket | Enforce Trailing Slash on URLs

Redirects the IPN URL to have a trailing slash so PayPal payments will not update correctly:

## Conditional Plugin Conflicts

### Asset CleanUp: Page Speed Booster

Note:  This issue is only present when the Asset CleanUp plugin is used with MemberPress and LearnDash together.

When used together with LearnDash, it prevents saving any changes in the LearnDash tab of a MemberPress membership:

### Curation Suite

JavaScript conflict prevents selecting auto-complete items in the MemberPress Rules:

### Elementor Popups

Note:  This issue is only present when the MemberPress registration form is added to Elementor Popup. Otherwise, Elementor works well with MemberPress.

Though MemberPress works well with Elementor in general, using the following shortcode in Elementor popups is not recommended:

```
[mepr-membership-registration-form id="123"]
```

Adding the above-mentioned shortcode to an Elementor popup results in the registration form not working correctly:

### Post and Page Builder from BoldGrid

When trying to delete a member at Dashboard > MemberPress > Members section, you'll get the message “The link you've followed has expired“, and the member will not get deleted:

### Power BI Embedded for WordPress

When activated, editing a MemberPress Rule will wipe out the content that should be protected:

### PushEngage Web Push Notifications

Note:  This issue is only present when the MemberPress coupons are used on the registration form. If you have coupons disabled, the PushEngage plugin should work well with MemberPress.

Breaks the MemberPress signup process when a coupon is applied:

### StreamWeasels

Note:  This issue is only present when creating courses with the MemberPress Courses addon.

MemberPress Courses curriculum is not displaying correctly after creating lessons:

### Yoast – Open Graph data

This is an edge case present only under the following conditions:

Unless the Open Graph description is manually added, Yoast will pull it in from your page or post content. Thus, if you’re using shortcodes on the MemberPress Account page (or custom account page), the shortcode could be pulled in as Open Graph data. This will create an issue with the MemberPress Gifting add-on and prevent the Send Gift pop-up from opening.

Note: This issue with the Gifting add-on only occurs when Open Graph data is enabled in the Yoast plugin settings. In all other cases, Yoast works well with both MemberPress and the Gifting add-on.

### WP Links Page

When enabled, it adds CSS to all pages of the wp-admin. This CSS inadvertently hides the access rows of the MemberPress Rules:

## Not Supported Plugins

### Complianz GDPR Premium

When active, this plugin will break Stripe Elements payments. Your customers will see the “An error occurred, please DO NOT submit the form again as you may be double charged” message:

### Constant Contact Forms

When active, this plugin will disrupt our Constant Contact add-on communication with the Constant Contact website, so it will fail to work:

### Custom Login Page Customizer

When enabled, login fails with the “ERROR: Error: Invalid email” message, though credentials are valid:

### Force SSL Everywhere plugin

The Force SSL Everywhere plugin overrides the user's login process and redirects them to wp-login.php. This causes the MemberPress registration process to fail, and no transaction is created for the member:

### GP Advanced Phone Field

When activated a Sign-Up button on the registration form is not working and the form cannot be submitted:

### Invisible ReCAPTCHA

When activated, password resets do not work. Usually, the member will see a blank page or an error when trying to reset their password:

### LearnPress – WordPress LMS Plugin

When the LearnPress plugin is active, the MemberPress Courses add-on doesn't work correctly.

### OptimizePress Suite Dashboard

MemberPress Courses lessons don't show on the front:

### Print Post and Page

Breaks the MemberPress signup process when using on-site payments like Stripe or Authorize.net:

### Role Scoper

Warning: This plugin has been closed as of January 7, 2022.

Buttons to add a new Membership or a new Group do not appear:

### Root Relative URLs

The plugin causes the Options page tabs not to work correctly.

### StreamWeasels

MemberPress Courses curriculum is not displaying correctly after creating lessons:

### White Label CMS

When the plugin is active, the WordPress Dashboard fails to load properly:

### WooCommerce Sync for QuickBooks Online – by MyWorks Software

When active, Stripe webhook communication frequently fails (but not all the time) with a “500 Internal Server Error” message:

When active, a password reset link generated from MemberPress's Login page causes a Fatal Error when clicked:

### WP Limit Login Attempts

Prevents users from logging in on the MemberPress login page. The page continues to refresh with no login:

### WP Multisite SSO

When enabled, it interferes with the Stripe checkout if a coupon is used, so the transaction never completes:

### WP Remote Users Sync

Incorrectly will throw the “Permissions” error message (as if the user doesn't have permission to purchase the membership) during registration. This only occurred with iOS/iPad OS users:

### WP Stagecoach

Incorrectly uses WordPress's plugin update transients. Breaks MemberPress' update mechanism and shows errors on your site:

### Yith WooCommerce Gift Cards

When this plugin is activated, you cannot upload files with our MP Downloads add-on:

Was this article helpful?

[Yes](https://memberpress.com)
[No](https://memberpress.com)

### Related Articles

[](https://memberpress.com/ads/70636/)

### Need Support?

Can't find the answer you're looking for?[Contact Support](https://memberpress.com)### Contents

 

### Helpful Articles

 

 

![computer girl](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSI0MDkiIGhlaWdodD0iMzY0IiB2aWV3Qm94PSIwIDAgNDA5IDM2NCI+PHJlY3Qgd2lkdGg9IjEwMCUiIGhlaWdodD0iMTAwJSIgc3R5bGU9ImZpbGw6I2NmZDRkYjtmaWxsLW9wYWNpdHk6IDAuMTsiLz48L3N2Zz4=)![computer girl](https://memberpress.com/wp-content/themes/memberpress-theme/images/FooterCTAgirl.webp)

### Get MemberPress today!

Start getting paid for the content you create.

[Get MemberPress Now](https://memberpress.com/plans/pricing/)

      Recommended by top influencers and web hosts
			

![4.8 out of 5 on Capterra](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzMDAiIGhlaWdodD0iMjEwIj48ZyBmaWx0ZXI9ImJsdXIoMTJweCkiPjxyZWN0IHdpZHRoPSIyMDAlIiBoZWlnaHQ9IjIwMCUiIHg9Ii01MCUiIHk9Ii01MCUiIGZpbGw9IiM5NGE0NWMiLz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSIjOTRhNDVjIi8+PGcgZmlsbC1vcGFjaXR5PSIuNSIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLjYgLjYpc2NhbGUoMS4xNzE4OCkiPjxlbGxpcHNlIGN4PSIxMzQiIGN5PSIxNDgiIGZpbGw9IiNmZmZjZDkiIHJ4PSI4MCIgcnk9IjEyNiIvPjxjaXJjbGUgcj0iMSIgZmlsbD0iIzAzMDAwMCIgdHJhbnNmb3JtPSJtYXRyaXgoMjQuNTY5OTkgLS41ODYxOSA0LjQ3NDggMTg3LjU2MDMgMTYgMTQ0LjIpIi8+PGNpcmNsZSByPSIxIiB0cmFuc2Zvcm09Im1hdHJpeCgtMy43MzgxNyAtMjE3LjUwODcgMjAuMTExMDUgLS4zNDU2MyAyNDEuNSAuMSkiLz48Y2lyY2xlIHI9IjEiIGZpbGw9IiNmZmYiIHRyYW5zZm9ybT0icm90YXRlKC0xNzcuNCA3Mi4zIDgxLjYpc2NhbGUoODEuMTk1OTQgMzMuMjkxNzMpIi8+PC9nPjwvZz48L3N2Zz4=)![4.8 out of 5 on Capterra](https://memberpress.com/wp-content/themes/memberpress-theme/images/capterra-footer.png)

![4.7 out of 5 on G2](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzMDAiIGhlaWdodD0iMjEwIj48ZyBmaWx0ZXI9ImJsdXIoMTJweCkiPjxyZWN0IHdpZHRoPSIyMDAlIiBoZWlnaHQ9IjIwMCUiIHg9Ii01MCUiIHk9Ii01MCUiIGZpbGw9IiM4Yzk0NTQiLz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSIjOGM5NDU0Ii8+PGcgZmlsbC1vcGFjaXR5PSIuNSIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLjYgLjYpc2NhbGUoMS4xNzE4OCkiPjxjaXJjbGUgcj0iMSIgZmlsbD0iIzI5MDAwMCIgdHJhbnNmb3JtPSJtYXRyaXgoMS4zODYxNyA1OS4yMTI2MyAtMjU0LjkzMDE1IDUuOTY3OTQgMTUwLjggMjQuMykiLz48Y2lyY2xlIHI9IjEiIGZpbGw9IiNmZmYiIHRyYW5zZm9ybT0ibWF0cml4KDc5LjIxODc1IC0xMy40NDQ0NyAxMC40NjY2MyA2MS42NzI0NiAxMTguNyAxNjUuNykiLz48Y2lyY2xlIHI9IjEiIHRyYW5zZm9ybT0icm90YXRlKC0xMS45IDI4OS4zIC0xMDU0Ljkpc2NhbGUoNDMuMTQxMjQgMjU1KSIvPjxlbGxpcHNlIGN4PSIxMjUiIGN5PSI5NCIgZmlsbD0iI2ZmODkwNiIgcng9IjEwMSIgcnk9IjQzIi8+PC9nPjwvZz48L3N2Zz4=)![4.7 out of 5 on G2](https://memberpress.com/wp-content/themes/memberpress-theme/images/g2-footer.png)

![4.8 out of 5 on Trust Pilot](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzMDAiIGhlaWdodD0iMjEwIj48ZyBmaWx0ZXI9ImJsdXIoMTJweCkiPjxyZWN0IHdpZHRoPSIyMDAlIiBoZWlnaHQ9IjIwMCUiIHg9Ii01MCUiIHk9Ii01MCUiIGZpbGw9IiM3NjdkNmEiLz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSIjNzY3ZDZhIi8+PGcgZmlsbC1vcGFjaXR5PSIuNSIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLjYgLjYpc2NhbGUoMS4xNzE4OCkiPjxjaXJjbGUgcj0iMSIgZmlsbD0iI2ZmZmZiOSIgdHJhbnNmb3JtPSJyb3RhdGUoLTE3NS44IDcxLjUgNjMuNSlzY2FsZSg4NC41MzUwMSAxMDcuNzM1NDEpIi8+PGNpcmNsZSByPSIxIiBmaWxsPSIjMDAxMjAwIiB0cmFuc2Zvcm09Im1hdHJpeCgzNi4zOTA1MyAxLjg2MzEgLTEyLjk4ODY3IDI1My42OTc1NCAxMiAzNi42KSIvPjxlbGxpcHNlIGN4PSIxMzgiIGN5PSIxNzAiIGZpbGw9IiNmZmYiIHJ4PSI4NCIgcnk9IjQyIi8+PGNpcmNsZSByPSIxIiB0cmFuc2Zvcm09InJvdGF0ZSgtMy43IDE0MDQuOCAtMzk1My42KXNjYWxlKDI4LjE3Mjk1IDIzOC44NTEzNCkiLz48L2c+PC9nPjwvc3ZnPg==)![4.8 out of 5 on Trust Pilot](https://memberpress.com/wp-content/themes/memberpress-theme/images/trustpilot-footer.png)

[](https://www.wpbeginner.com/plugins/5-best-wordpress-membership-plugins-compared/)

![Easiest Admin - Summer 2024](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyOTkiIGhlaWdodD0iMzg5Ij48ZyBmaWx0ZXI9ImJsdXIoMTJweCkiPjxyZWN0IHdpZHRoPSIyMDAlIiBoZWlnaHQ9IjIwMCUiIHg9Ii01MCUiIHk9Ii01MCUiIGZpbGw9IiM4ODgiLz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSIjODg4Ii8+PGcgZmlsbC1vcGFjaXR5PSIuNSIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLjggLjgpc2NhbGUoMS41MTk1MykiPjxlbGxpcHNlIGN4PSI5NCIgY3k9IjcyIiBmaWxsPSIjZmZmZmVjIiByeD0iMTI3IiByeT0iMTYzIi8+PGNpcmNsZSByPSIxIiB0cmFuc2Zvcm09InJvdGF0ZSgtMTIyLjUgMTU4IDc1LjQpc2NhbGUoMzUuNTQ1NDYgOTcuNjIwNDgpIi8+PGNpcmNsZSByPSIxIiB0cmFuc2Zvcm09InJvdGF0ZSgzMiAtNDI4LjcgMTg0LjYpc2NhbGUoNTIuNTYxNDEgMzAuODAyOTgpIi8+PGNpcmNsZSByPSIxIiBmaWxsPSIjZmRlNzRlIiB0cmFuc2Zvcm09Im1hdHJpeCgxODQuMjkzMSAuNDg3NyAtLjA3OTE0IDI5LjkwNDggMTE1LjEgMTUwLjcpIi8+PC9nPjwvZz48L3N2Zz4=)![Easiest Admin - Summer 2024](https://memberpress.com/wp-content/themes/memberpress-theme/images/verification-badges/easiest-admin.png)

![Easiest Setup - Summer 2024](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyOTkiIGhlaWdodD0iMzg5Ij48ZyBmaWx0ZXI9ImJsdXIoMTJweCkiPjxyZWN0IHdpZHRoPSIyMDAlIiBoZWlnaHQ9IjIwMCUiIHg9Ii01MCUiIHk9Ii01MCUiIGZpbGw9IiM4MzgzODMiLz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSIjODM4MzgzIi8+PGcgZmlsbC1vcGFjaXR5PSIuNSIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLjggLjgpc2NhbGUoMS41MTk1MykiPjxlbGxpcHNlIGN4PSI5NCIgY3k9IjM0IiBmaWxsPSIjZmZmIiByeD0iMTQyIiByeT0iMjAzIi8+PGNpcmNsZSByPSIxIiB0cmFuc2Zvcm09InJvdGF0ZSgtMjggNTU2LjIgLTI3OC45KXNjYWxlKDkwLjAxMzk0IDI0Ljg4NTU3KSIvPjxjaXJjbGUgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoLTYuOTcyNTcgMjkuMzE4ODggLTQ3LjY0MjQ2IC0xMS4zMzAyNSAxOSAyNDguOCkiLz48ZWxsaXBzZSBjeD0iMTIwIiBjeT0iMTQzIiBmaWxsPSIjNWRjNWZmIiByeD0iMTk2IiByeT0iMjQiLz48L2c+PC9nPjwvc3ZnPg==)![Easiest Setup - Summer 2024](https://memberpress.com/wp-content/themes/memberpress-theme/images/verification-badges/easiest-setup.png)

![High Performer - Summer 2024](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyOTkiIGhlaWdodD0iMzg5Ij48ZyBmaWx0ZXI9ImJsdXIoMTJweCkiPjxyZWN0IHdpZHRoPSIyMDAlIiBoZWlnaHQ9IjIwMCUiIHg9Ii01MCUiIHk9Ii01MCUiIGZpbGw9IiM3NDc0NzQiLz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSIjNzQ3NDc0Ii8+PGcgZmlsbC1vcGFjaXR5PSIuNSIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLjggLjgpc2NhbGUoMS41MTk1MykiPjxlbGxpcHNlIGN4PSI5OCIgY3k9IjgyIiBmaWxsPSIjZmZmIiByeD0iMTIyIiByeT0iMTU3Ii8+PHBhdGggZD0ibTIzMC43IDIzOC4yLTc1LjUgNDcuMi0yNi00MS42IDc1LjYtNDcuMnoiLz48Y2lyY2xlIHI9IjEiIGZpbGw9IiNmZmYiIHRyYW5zZm9ybT0ibWF0cml4KDYxLjI1ODEgOC4xNzM1OCAtOC42NDg3NiA2NC44MTk0NyAxNy4xIDU0LjEpIi8+PGNpcmNsZSByPSIxIiB0cmFuc2Zvcm09Im1hdHJpeCg5OC40ODI2OCA2NS45NzcwMyAtMjAuMTIyNzIgMzAuMDM2ODEgMTUuNSAyNTUpIi8+PC9nPjwvZz48L3N2Zz4=)![High Performer - Summer 2024](https://memberpress.com/wp-content/themes/memberpress-theme/images/verification-badges/high-performer.png)

![Momentum Leader - Summer 2024](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyOTkiIGhlaWdodD0iMzg5Ij48ZyBmaWx0ZXI9ImJsdXIoMTJweCkiPjxyZWN0IHdpZHRoPSIyMDAlIiBoZWlnaHQ9IjIwMCUiIHg9Ii01MCUiIHk9Ii01MCUiIGZpbGw9IiM3NDc0NzQiLz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSIjNzQ3NDc0Ii8+PGcgZmlsbC1vcGFjaXR5PSIuNSIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLjggLjgpc2NhbGUoMS41MTk1MykiPjxlbGxpcHNlIGN4PSI5MyIgY3k9IjgxIiBmaWxsPSIjZmZmIiByeD0iMTMyIiByeT0iMTU2Ii8+PGNpcmNsZSByPSIxIiB0cmFuc2Zvcm09Im1hdHJpeCgtNjIuMDU3MjMgNDAuMjcxNjkgLTEzLjgzMDI1IC0yMS4zMTE5MyAxNzkuOCAyMzkuOCkiLz48Y2lyY2xlIHI9IjEiIHRyYW5zZm9ybT0ibWF0cml4KC0xNC40NTcwNCAtMzEuMTQ1MDIgNDYuMDc4MTkgLTIxLjM4ODc4IDEzLjQgMjU1KSIvPjxjaXJjbGUgY3g9Ijc0IiByPSIyMTQiIGZpbGw9IiNmZmQyYzkiLz48L2c+PC9nPjwvc3ZnPg==)![Momentum Leader - Summer 2024](https://memberpress.com/wp-content/themes/memberpress-theme/images/verification-badges/momentum-leader.png)

## Footer

 

#### Company

#### Features

#### Integrations

#### Case Studies

#### Helpful Links

 

![MemberPress logo](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7)![MemberPress logo](https://memberpress.com/wp-content/themes/memberpress-theme/images/memberpress-logo-white.svg)

[](https://twitter.com/memberpress)
[](https://facebook.com/memberpress)
[](https://www.instagram.com/memberpress)
[](https://www.youtube.com/c/MemberPressPlugin)

						Copyright © 2025 Caseproof, LLC. All rights reserved.
					

[Privacy Policy](https://memberpress.com/privacy/)
/
[Refunds](https://memberpress.com/terms/#refunds)
/
[Terms & Conditions](https://memberpress.com/terms/)
/
[FTC Disclosure](https://memberpress.com/privacy/)
/
[MemberPress Coupon Code](https://memberpress.com/memberpress-coupon-code/)

 

Username or E-mail

Password

 Remember Me

 

 

[Forgot Password](https://memberpress.com/sign-in/?action=forgot_password)

			×			

 

  ![](https://px.ads.linkedin.com/collect/?pid=3219420&fmt=gif)

