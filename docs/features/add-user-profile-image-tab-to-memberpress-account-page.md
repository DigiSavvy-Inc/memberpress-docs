# Add User Profile Image Tab to MemberPress Account Page

## Additional menu

[](https://memberpress.com/)MemberPress

The All-In-One WordPress Membership Plugin

 

![worker bees](https://memberpress.com/wp-content/themes/memberpress-theme/images/memberpress-logo-color.svg)

				Get MemberPress today! Start getting paid for the content you create!

[Get MemberPress Now](https://memberpress.com/plans/pricing/)

Search For

Search

# How to Add User Profile Image tab to the Account page?

If you're looking to have a user profile image tab on the Account page where users can easily add their profile image and use it through your website, look no further than theOne User Avatar plugin.

To add a user profile image tab, please follow the steps below:

![Contributor and Subscriber Avatar Settings](data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzMDAiIGhlaWdodD0iMTMwIj48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSIjNGM0YzRjIi8+PGcgZmlsbC1vcGFjaXR5PSIuNSIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLjYgLjYpc2NhbGUoMS4xNzE4OCkiPjxjaXJjbGUgY3g9IjE0MCIgY3k9IjU0IiByPSIxNTciIGZpbGw9IiNmZmYiLz48Y2lyY2xlIGN4PSIxNDUiIGN5PSI5MiIgcj0iMTk0IiBmaWxsPSIjZmZmIi8+PGNpcmNsZSByPSIxIiBmaWxsPSIjZWRlZGVkIiB0cmFuc2Zvcm09InJvdGF0ZSgxNzcuNSA2NS40IDI4LjYpc2NhbGUoMTc3LjAzNDA1IDg4LjQxMDg5KSIvPjxwYXRoIGZpbGw9IiNlMGUwZTAiIGQ9Im0xMzcuMiAxNy4zLTE0IDEzLjYgMTIuNy0yMyAxMy4zIDI3LjV6Ii8+PC9nPjwvc3ZnPg==)

### Use Custom Functions

If you are familiar with PHP, you can add the code below at the bottom of your active theme's function or use the WPCode plugin (please check this article for details: How to add custom code snippets in WPCode).

```
<?php
function mepr_add_image_tab($user) {
    ?>
    <span class="mepr-nav-item custom-image">
      <a href="/index.php/account/?action=profile-image">Profile Image</a>
    </span>
    <?php
}
add_action('mepr_account_nav', 'mepr_add_image_tab');

function mepr_add_image_tab_content($action) {
    if($action == 'profile-image') {
        echo do_shortcode('[avatar_upload]');
    }
}
add_action('mepr_account_nav_content', 'mepr_add_image_tab_content');
?>
```

## Displaying profile image

Adding a user profile image like this will change the user picture called avatar in all places where the user picture is displayed. It will also replace the user image from the Gravatar site assigned to the user's email. The most popular place where the user picture is displayed is the post comments, but you can display it anywhere using the following shortcode:

```
[avatar user="current"]
```

Was this article helpful?

[Yes](https://memberpress.com)
[No](https://memberpress.com)

### Related Articles

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

