# Overview of Using the MemberPress Developer Tools Addon | MemberPress

## Additional menu

[](https://memberpress.com/)MemberPress

The All-In-One WordPress Membership Plugin

 

![worker bees](https://memberpress.com/wp-content/themes/memberpress-theme/images/memberpress-logo-color.svg)

				Get MemberPress today! Start getting paid for the content you create!

[Get MemberPress Now](https://memberpress.com/plans/pricing/)

Search For

Search

# Overview of Using the MemberPress Developer Tools Addon

Note: This integration is available to MemberPress Plus and Pro plan members. If you're subscribed to the Basic plan, you will need to upgrade to Plus or Pro. To upgrade, click the Change Plan link on your account page.

Note: If you're not a developer, you might find our Zapier integration, WP Fusion, or the Uncanny Automator easier to use.

MemberPress Developer Tools Add-on extends MemberPress to include a full REST API and full Webhook event capability.

Note: Please note that starting from version 1.2.14, we have removed the password argument for member create and update since it presents a security risk.

If the documentation on this page seems light for developer tools, that's because all the documentation for the webhook events and REST API URLs can be found in the plugin's interface. The interface will actually give you dynamic results to work from and the ability to test webhooks directly from your site. You may also refer to the following additional docs for more info:

## Getting started couldn't be easier… here's how

## Sample PHP cURL Code

This example adds a Member, assigns them to a Membership (via a transaction), and triggers a welcome email in the process:

```
<?php
$url = 'http://testsite.w6.wpsandbox.pro/wp-json/mp/v1/members';

$ch = curl_init($url);

$data_string = json_encode(
  [
    'email'               => 'testingboy897@test.com',
    'username'            => 'testingboy897@test.com',
    'first_name'          => 'test',
    'last_name'           => 'test_last_name',
    'send_welcome_email'  => true, // Trigger a welcome email - this only works if adding a transaction (below)
    'transaction'         => [
      'membership'  => 376, // ID of the Membership
      'amount'      => '0.00',
      'total'       => '0.00',
      'tax_amount'  => '0.00',
      'tax_rate'    => '0.000',
      'trans_num'   => 'mp-txn-' . uniqid(),
      'status'      => 'complete',
      'gateway'     => 'free',
      'created_at'  => gmdate( 'c' ),
      'expires_at'  => '0000-00-00 00:00:00'
    ]
  ]
);

curl_setopt( $ch, CURLOPT_RETURNTRANSFER, true );
curl_setopt( $ch, CURLOPT_CUSTOMREQUEST, "POST" );
curl_setopt( $ch, CURLOPT_POSTFIELDS, $data_string );

$header = array();
$header[] = 'MEMBERPRESS-API-KEY: MgCUGSO5Qg'; // Your API KEY from MemberPress Developer Tools Here
$header[] = 'Content-Type: application/json';
$header[] = 'Content-Length: ' . strlen($data_string);
curl_setopt($ch, CURLOPT_HTTPHEADER, $header);

$response = curl_exec($ch);

if(curl_errno($ch)){
  throw new Exception(curl_error($ch));
}

echo $response;

curl_close($ch);
```

## Webhook Key

Since MemberPress Developer Tools Add-on 1.2.5, we introduced a Webhook Key setting that can be found in the MemberPress menu > Developers > Webhook tab.

You can use the key to authenticate webhook POST requests. It is generated automatically by the MemberPress add-on, but if you feel your key has been compromised, you can regenerate a new webhook key at any time.

To validate the webhook request, fetch HTTP headers and look for memberpress-webhook-key. Here's an example of an HTTP header with memberpress-webhook-key received after creating a new Webhook URL in the MemberPress menu > Developers > Webhook tab and listening to signup events:

## Troubleshooting Basic Authentication

The preferred method for authentication is via the API Key provided by MemberPress Developer Tools. However, we know that many of you also use the less secure – Basic Authentication method – to connect to the WP-API. However, this can present a few challenges, which the information below can assist you with.

If you're struggling to get Basic Authentication to work, be sure you've
installed the Application Passwords plugin and followed its instructions.

A typical Basic Auth request be as follows:

	 Header Name:
Authorization
	 Header Value: 
Basic base64_encode( wp_admin_user_login_here:application_passwords_password_here )

Your user should have the
remove_users capability, or MemberPress Developer Tools will return a 401 response.

If you're still unable to authenticate, then your hosting server may have some configuration issues.
Read more about the most common cause here. The Application Passwords plugin must have the PHP_AUTH_USER and PHP_AUTH_PW variables set. If they're not set, Application Passwords will fail to authenticate the user, and you'll need to work with your webhost to correct it. Typically it requires adding something like the following to the .htaccess file:

```
SetEnvIf Authorization "(.*)" HTTP_AUTHORIZATION=$1
```

If all else fails, it's best to just use the API Key in the 
MEMBERPRESS-API-KEY HTTP request header instead. Below is some sample code with the API Key and PHP cURL:

```
<?php
$url = 'http://testsite.com/wp-json/mp/v1/me';
$ch = curl_init( $url );
curl_setopt( $ch, CURLOPT_RETURNTRANSFER, true );
$headers = [ 'MEMBERPRESS-API-KEY: MdCUPSO5Qr', 'Content-Type: application/json' ];
curl_setopt( $ch, CURLOPT_HTTPHEADER, $headers );
$response = curl_exec( $ch );
if( curl_errno( $ch ) ) { throw new Exception( curl_error( $ch ) ); }
curl_close($ch);
echo $response;
```

## Troubleshooting Webhooks

If your test webhooks are working, but your live tests are not firing, then WP Cron is most likely disabled or is not working as it should. MemberPress Developer Tools rely on WP Cron to send out the webhooks.

In this case, the easiest way to verify is to check the wp_mepr_jobs table in your database to see if the webhook jobs are stuck there with a status of “pending”.

When possible, we recommend disabling page load based WP Cron and instead triggering it from a server-side cron that runs every minute. SiteGround has a great article on
doing this here. And WordPress.org has some additional information here. Unfortunately, we can't assist you with this, and your webhost will need to help you set it up.

If you're unable to get WP Cron firing correctly, even after enabling a server-side cron, then you may (as a last resort) need to issue the following query:

```
UPDATE wp_options SET option_value = '' WHERE option_name = 'cron';
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

