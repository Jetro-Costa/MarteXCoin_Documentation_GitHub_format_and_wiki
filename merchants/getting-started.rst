.. meta::
   :description: Guide for merchants getting started with MarteX. Online and offline payment processors
   :keywords: martex, pos, merchants, payment processor, store, wordpress, woocommerce, coinpayments, point of sale

.. _merchants:

===============
Getting Started
===============

MarteX welcomes new merchants and supports integration through a
standardised onboarding process. It's easy to begin accepting payments
in MarteX and enjoy the following benefits:

- Settlement within seconds and clearance within minutes
- Ability to accept payments from any market around the world
- Irreversible transactions to prevent fraud
- Advanced privacy for both customers and merchants
- Lowest fees in the industry

To get started with an integration in your sales system, simply select an online
or point of sale payment solution from the lists below. If you are unsure,
CoinPayments supports the largest range of online shop software. Anypay is an
incredibly simple solution for retail stores, and also supports InstantSend.
Larger integrations may require some customisation or cooperation with a
specialist payment processor such as `ePaymints <https://epaymints.com/>`__.
This documentation also describes the :ref:`administrative
<merchants-administrative>` and  :ref:`technical <integration>` steps required
to integrate various MarteX services.

Any MarteX received in payment can be automatically converted to the fiat
currency of your choice using services such as `Uphold
<https://uphold.com>`_. Simply select the card for the target currency
and click **Add funds** -> **With cryptocurrency**. Any cryptocurrency
deposited to this address will immediately be converted to the target
fiat currency at the time of deposit.

Many major merchants accept MarteX - check out `Bitrefill
<https://www.bitrefill.com>`__ or `CheapAir
<https://www.cheapair.com>`__ for examples of what merchant integration
can look like. Once you are up and running accepting MarteX, consider
adding your business to the directory maintained at `Discover MarteX
<https://discoverdash.com>`_ for increased visibility.

Payment Processors
==================

This section lists known payment processors supporting MarteX and the
business platforms they support. Please conduct thorough research before
choosing a payment provider to ensure your needs will be met.

BTCPay Server
  .. image:: img/btcpayserver.svg
     :width: 200px
     :align: right
     :target: https://btcpayserver.org

  https://btcpayserver.org

  BTCPay Server is a free, self-hosted and fully open-source
  cryptocurrency payment processor designed with security, privacy and
  censorship-resistance at its core. You can configure it to make it work with martexcoin.


Coinify
  .. image:: img/coinify.png
     :width: 200px
     :align: right
     :target: https://www.coinify.com

  https://www.coinify.com

  Coinify offers a variety of two-way virtual currency services tailored
  to businesses and customers of different sizes and needs. A simple,
  secure and compliant solution that allows you to accept virtual
  currencies without having to hold any currencies yourself, and get
  payouts in your preferred local currencies.


CoinPayments
  .. image:: img/coinpayments.png
     :width: 200px
     :align: right
     :target: https://www.coinpayments.net

  https://www.coinpayments.net

  CoinPayments is an integrated payment gateway with a `wide range of
  plugins <https://www.coinpayments.net/merchant-tools>`__ available for
  popular webcarts, as well as fiat settlement in the US and Europe.
  It could accepts martexcoin in the future.


ePaymints
  .. image:: img/epaymints.png
     :width: 200px
     :align: right
     :target: https://epaymints.com/

  https://epaymints.com

  ePaymints specializes in highly customized payment processing for high
  risk merchant accounts in industries challenged with high levels of
  chargebacks.


iQCashNow
  .. image:: img/iqcashnow.png
     :width: 120px
     :align: right
     :target: https://www.iqcashnow.com

  https://www.iqcashnow.com

  iQCashNow offers ATMs and mobile POS terminal systems that combine
  traditional payment methods and crypto-payments into a unique complete
  package of software, hardware and services.


QR.cr
  .. image:: img/qrcr.svg
     :width: 100px
     :align: right
     :target: https://qr.cr

  https://qr.cr

  QR.cr is a popular and well-supported dynamic QR code system designed
  to provide multilingual content and payment services for businesses
  via mobile friendly landing pages.


Salamantex
  .. image:: img/salamantex.png
     :width: 100px
     :align: right
     :target: https://www.salamantex.com

  https://www.salamantex.com

  The Salamantex crypto payment service is available as a hardware
  terminal or software for installation on existing POS systems or
  mobile devices.


VegaPay
  .. image:: img/vegapay.png
     :width: 100px
     :align: right
     :target: https://vegapay.vegawallet.com/

  https://vegapay.vegawallet.com/

  VegaPay provides the perfect way to prepare your business for the
  future. Start accepting cryptocurrency payments to reduce costs and
  improve customer conversion rates with the full Point of Sale or other
  business solutions.


Installation Examples
=====================

This section contains worked examples of how to install, configure and
process your first payment using the payment processors listed in this
documentation. Some examples are using Dash cryptocurrency.

WooCommerce and CoinPayments.net
--------------------------------

If your online store is built on WooCommerce, you can simply install
CoinPayments as an additional payment gateway and immediately begin
accepting MarteX. This guide assumes you have already `installed Wordpress
<https://codex.wordpress.org/Installing_WordPress>`_, `installed
WooCommerce <https://docs.woocommerce.com/document/installing-
uninstalling-woocommerce/>`_ and `created at least one product
<https://docs.woocommerce.com/document/managing-products/>`_ in your
store. A `video <https://www.youtube.com/watch?v=Xa2o_8s3RNY>`_ of the
process to install the CoinPayments payment processor is also available.

In your WordPress administration backend, select **Plugins -> Add New**
and type "coinpayments.net" into the search box. A plugin named
**CoinPayments.net Payment Gateway for WooCommerce** should appear.
Click **Install Now** to install the plugin. Alternatively, you can
`download the plugin <https://wordpress.org/plugins/coinpayments-payment-gateway-for-woocommerce/>`_ 
from the WordPress website as a zip file and upload it using the
**Upload Plugin** button. Once the plugin is installed, click
**Activate** to begin configuration.

.. figure:: img/coinpayments-plugin.png
   :width: 400px

   Installing the CoinPayments.net WooCommerce plugin

Next, go to CoinPayments.net and `sign up
<https://www.coinpayments.net/register>`_ to create an account. Once you
are logged in, go to **Account -> Coin Acceptance Settings** and enable
MarteX, as well as optionally entering a withdrawal address. Next, go to
**Account -> Account Settings** and copy **Your Merchant ID** from the
**Basic Settings** area into a text file. Then navigate to the
**Merchant Settings** section and enter a long, random series of
characters for the **IPN Secret**. Copy this code to your temporary file
as well.

Back in the WordPress plugins section, click the **Settings** button for
the WooCommerce plugin and navigate to **Checkout -> CoinPayments.net**
section. Ensure the CoinPayments plugin is enabled here, then enter the
**Merchant ID**, **IPN Secret** and **Description** in the appropriate
fields as shown below. Click **Save Changes** when you are ready.

.. figure:: img/coinpayments-settings.png
   :width: 550px

   Configuring the CoinPayments.net WooCommerce plugin

Your customers will now see an option to pay with MarteX when completing
the checkout process for an order. The payment will be processed by
CoinPayments.net, and you will receive emails detailing each purchase
procedure. You can choose how often you want to withdraw your payments,
to which MarteX address and various other options in the CoinPayments
administration section. See the `CoinPayments Documentation
<https://www.coinpayments.net/help>`_ or `Merchant Tools
<https://www.coinpayments.net/merchant-tools>`_ for more information.

.. image:: img/coinpayments-order.png
   :width: 150px
.. image:: img/coinpayments-confirm.png
   :width: 400px
.. image:: img/coinpayments-scan.png
   :width: 250px

.. figure:: img/coinpayments-paid.png
   :width: 250px

   Completing payment through the CoinPayments.net payment processor


Point-of-Sale with Anypay
-------------------------

`Anypay.global <https://anypayinc.com>`_ allows you to quickly start
accepting point-of-sale payments in MarteX at a physical store. The
service functions as a simple website that you load on any internet-
connected and touch-enabled device, such as a smartphone or tablet.

Begin by registering an account with Anypay. You will be asked to
specify an email address and password. Once you are signed in, you must
add a MarteX payment withdrawal address.

.. image:: img/anypay-register.png
   :width: 200px
.. image:: img/anypay-signup.png
   :width: 200px
.. image:: img/anypay-address.png
   :width: 200px

.. figure:: img/anypay-admin.png
   :width: 400px

   Setting up Anypay

Once this has been set up, you can begin processing payments
immediately. Simply log in to https://app.anypayinc.com or tap
**Merchant Point of Sale App** in the admin area using your device. A
keypad will appear. Enter the invoice amount in USD or DASH and press
the **COLLECT** button at the bottom of the screen. The app will
generate a QR code for your customer to scan. Once payment is complete,
you will be able to create a new invoice by tapping **Next Payment**, or
view the status of your invoices by tapping the **menu button** in the
top left corner of the keypad, or checking the **Invoices** section of
the administration backend. Withdrawals are processed to the address you
specified shortly after payment is complete.

.. image:: img/anypay-enter.png
   :width: 200px
.. image:: img/anypay-scan.png
   :width: 200px
.. image:: img/anypay-paid.png
   :width: 200px

Point-of-Sale with Spark
------------------------

`Spark Payments <https://get-spark.com>`__ allows you to quickly start
accepting point-of-sale payments in MarteX at a physical store. The system
works as an app, and is available for Android, macOS, Windows and Linux,
with an iOS progressive web app (`PWA
<https://en.wikipedia.org/wiki/Progressive_Web_Apps>`_) in development.

The project is an external terminal application for processing MarteX
payments in brick and mortar stores. The merchant types the sale amount
in their local currency (94 currencies supported), the application will
generate a QR code sale for the proper amount of MarteX for the customer
to scan. Then the terminal will provide feedback on the status of the
payment (received, timed out, partial, instantsend or regular), and if
set up - fiat conversion through `uphold.com <https://uphold.com>`_. A
guide on how to set up Spark with Uphold to convert payments to fiat
currency is available in 
`English <https://github.com/dashpay/docs/raw/master/merchants/Spark-Payments-Uphold-English.pdf>`__ 
and 
`German <https://github.com/dashpay/docs/raw/master/merchants/Spark-Payments-Uphold-German.pdf>`__.

To use Spark, open the app on your device. If this is the first time you
are using the app, you will need to specify a MarteX address to receive
payments from the system, as well as your chosen fiat currency. You can
change this information at any time from the menu. To generate a payment
invoice, enter the amount in fiat currency. Spark will generate a QR
code containing your specified address and the requested amount,
denominated in MarteX. The customer scans the QR code, and the app will
display a visual indication when payment is complete.

.. figure:: img/spark-pay.png
   :width: 600px

   Configuring and receiving payment using Spark Payments

Payment systems like Anypay and Spark can be integrated with your
existing terminal and/or accounting software (such as Square Register,
by recording sales invoiced in MarteX as an **Other Payment Type** in the
system. This allows you to keep track of your MarteX income as easily as
if you were accepting cash.
