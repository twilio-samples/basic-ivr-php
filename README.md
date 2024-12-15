# Basic Twilio IVR with PHP

<!-- markdownlint-disable MD013 -->
This app shows how to build a basic [IVR (Interactive voice response)][twilio_ivr_url] system with PHP and Twilio.

## Overview

- A user calls their Twilio phone number
- The user is then presented with 3 options: 1) Talk to sales, 2) The company's hours of operation, or 3) The company's address
- If the user chooses one of the first two options, they get a voice response on the call with more information
- If they choose the third option, they will receive an SMS with the company's address information

## Prerequisites/Requirements

To run the code, you will need the following:

- PHP 8.3
- [Composer][composer_url] installed globally
- A network testing tool such as [curl][curl_url] or [Postman][postman_url]
- [ngrok][ngrok_url] and a free ngrok account
- A Twilio account (free or paid) with an active phone number that can send SMS.
  If you are new to Twilio, [create a free account][twilio_referral_url]

## ⚡️ Quick Start

After cloning the code to wherever you store your PHP projects, change into the project directory.
Then, install PHP's dependencies and copy _.env.example_ as _.env_, by running the following commands:

```bash
composer install
cp -v .env.example .env
```

After that, set values for `TWILIO_ACCOUNT_SID`, `TWILIO_AUTH_TOKEN`, `TWILIO_PHONE_NUMBER`.
You can retrieve these details from the **Account Info** panel of your [Twilio Console](https://console.twilio.com/) dashboard.

![A screenshot of the Account Info panel in the Twilio Console dashboard. It shows three fields: Account SID, Auth Token, and "My Twilio phone number", where Account SID and "My Twilio phone number" are redacted.](docs/images/twilio-console-account-info-panel.png)

Then, set `MY_PHONE_NUMBER` to the phone number that you want to receive SMS notifications to.
Ideally, also set as many of the commented out configuration details as possible.

When that's done, run the following command to launch the application:

```php
composer serve
```

Then, use ngrok to create a secure tunnel between port 8080 on your local development machine and the public internet, making the application publicly accessible, by running the following command.

```php
ngrok http 8080
```

Now, you're ready to go.

## Contributing

If you want to contribute to the project, whether you have found issues with it or just want to improve it, here's how:

- [Issues][issues_url]: ask questions and submit your feature requests, bug reports, etc
- [Pull requests][pull_requests_url]: send your improvements

## Did You Find The Project Useful?

If the project was useful, and you want to say thank you and/or support its active development, here's how:

- Add a GitHub Star to the project
- Write an interesting article about the project wherever you blog

## License

[MIT][mit-license-url]

## Disclaimer

No warranty expressed or implied. Software is as is.

[composer_url]: https://getcomposer.org
[curl_url]: https://curl.se/
[issues_url]: https://github.com/settermjd/basic-ivr-php/issues
[mit-license-url]: http://www.opensource.org/licenses/mit-license.html
[ngrok_url]: https://ngrok.com/
[postman_url]: https://www.postman.com/
[pull_requests_url]: https://github.com/settermjd/basic-ivr-php/pulls
[twilio_ivr_url]: https://www.twilio.com/en-us/use-cases/ivr
[twilio_referral_url]: https://login.twilio.com/u/signup?state=hKFo2SA5Qlp2bThzaGh4T0RnUDJMU0c4VWxhZ0lYRUZrQlMxMqFur3VuaXZlcnNhbC1sb2dpbqN0aWTZIDVKUmh0dFM4ZTV0cmt2QkdKeVp6R212Z2JiMlE2U0R6o2NpZNkgTW05M1lTTDVSclpmNzdobUlKZFI3QktZYjZPOXV1cks
<!-- markdownlint-enable -->
