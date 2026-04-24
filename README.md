# Build a phone menu (IVR)

This app shows how to build a basic [phone menu (<abbr>IVR</abbr> Interactive Voice Response)][twilio_ivr_url] system with PHP and Twilio.

## IVR overview

This sample app provides the following functionality:

1. A customer calls your Twilio phone number
2. Your app answers the call using text-to-speech and asks the caller to choose from one of three options:
    1. Talk to sales 
    2. Get the company's hours of operation
    3. Get the company's address
3. The caller dials an option. Your app tells them the information that they requested or it sends an SMS to the caller with the company's address.

## Prerequisites

To run the app locally, you need the following:

- PHP 8.3 or later
- [Composer][composer]
- A network testing tool such as [curl][curl_url], [Resterm][resterm_url], or [Postman][postman_url]
- An [ngrok][ngrok] account
- A [Twilio account][twilio-signup] with an active phone number that can send SMS

## Quickstart

1. Clone or download this repository.
2. Install the dependencies:
    ```bash
    composer install
    ```
3. Rename the `.env.example` file to `.env`
4. Go to the [Twilio Console][twilio-console] and find your **Account SID**, **Auth Token**, and Twilio phone number.
5. Copy and paste those values into the placeholders in the `.env` file. Save the file.
6. Start the app:
    ```bash
    composer run-script serve
    ```
7. Start your ngrok server:
    ```bash
    ngrok http 8080
    ```
8. Go to the [Active numbers][active-numbers] page in the Twilio Console.
9. Click your Twilio phone number.
10. Go to the **Configure** tab and find the **Voice Configuration** section.
11. In the **A call comes in** row, select the **Webhook** option.
12. Paste your ngrok public URL in the **URL** field. For example, if your ngrok console shows Forwarding `https://1aaa-123-45-678-910.ngrok-free.app`, enter `https://1aaa-123-45-678-910.ngrok-free.app`.
13. Click **Save configuration**.
14. With the PHP server and ngrok running, call your Twilio phone number. You hear the IVR greeting defined in `public/index.php`.

## Testing

This project uses PHPUnit for testing. To run tests:

```bash
composer test
```

[composer]: https://getcomposer.org
[curl_url]: https://curl.se/
[ngrok]: https://ngrok.com/
[postman_url]: https://www.postman.com/
[resterm_url]: https://github.com/unkn0wn-root/resterm
[twilio-signup]: https://www.twilio.com/try-twilio
[twilio-console]: https://console.twilio.com/
[active-numbers]: https://www.twilio.com/console/phone-numbers/incoming
[twilio-ivr-url]: https://www.twilio.com/en-us/use-cases/ivr
