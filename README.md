# RNPay
A sample app showing how to use the Tipsi-Stripe library for handling payments in React Native with a Lumen PHP backend. 

You can read the tutorial at: [Accepting payments in React Native](https://pusher.com/tutorials/react-native-payments)

### Prerequisites

- React Native development environment or [Expo](https://expo.io/)
- PHP development environment - you can use either [Laravel Homestead](https://laravel.com/docs/5.7/homestead) or [Valet](https://laravel.com/docs/5.7/valet).
- [Ngrok account](https://ngrok.com/)
- [Google Play developer console account](https://play.google.com/apps/publish/signup/#)
- [Apple developer account](https://developer.apple.com/programs/enroll/)
- [Stripe account](https://stripe.com/)
- MySQL database manager - [DBeaver](https://dbeaver.io/), [SequelPro](https://www.sequelpro.com/)


## Getting Started

1. Clone the repo:

```
git clone https://github.com/anchetaWern/RNPay.git
```

2. Install the dependencies:

```
cd RNPay
yarn install
react-native eject
react-native link
```

3. Create a new Lumen project:

```
composer create-project --prefer-dist laravel/lumen RNPayBackend
```

4. Copy the files from the `server/RNPayBackend` directory to the newly generated `RNPayBackend` folder.

5. Create the `rnpay` database with a MySQL database manager of your choice.

6. Update the `.env` file with the database config and Stripe secret key:

```
DB_USERNAME=YOUR_DB_USER
DB_PASSWORD=YOUR_DB_PASSWORD
STRIPE_SECRET_KEY=YOUR_STRIPE_SECRET_KEY
```

7. Run the migration:

```
php artisan migrate
```

8. Expose the server with ngrok:

```
ngrok http -host-header=rewrite rnpay.test:80
```

9. Go inside the `RNPay` directory and update the `.env` file with your Stripe publishable key:

```
STRIPE_PUBLISHABLE_KEY=YOUR_STRIPE_PUBLISHABLE_KEY
```

10. Update the `src/helpers/pay.js` file with your ngrok URL:

```
const endpoint = 'https://YOUR_NGROK_URL/charge';
```

11. Run the app:

```
react-native run-android
```

## Built With

* [React Native](http://facebook.github.io/react-native/)
* [Lumen PHP framework](https://lumen.laravel.com/)

## Donation

If this project helped you reduce time to develop, please consider buying me a cup of coffee :)

<a href="https://www.buymeacoffee.com/wernancheta" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png" alt="Buy Me A Coffee" style="height: 41px !important;width: 174px !important;box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;" ></a>
