
GoUrl.io Bitcoin/Altcoin Payment Gateway API ASP .NET C#
-----------------------------------------

Version 1.0.5

**Accept Bitcoin, Litecoin, Dogecoin, Dash, Speedcoin, Reddcoin, Potcoin, Feathercoin, Vertcoin, Vericoin, Peercoin, Paycoin, MonetaryUnit, Swiscoin Payments Online on your ASP.NET C# website**


Copyright &copy; 2014-2017 [Delta Consultants](https://gourl.io)

Website: [https://gourl.io](https://gourl.io)

API NuGet ASP .NET MVC: https://www.nuget.org/packages/GoUrl.io/

API Bitcoin ASP.NET Instruction: [https://gourl.io/bitcoin-api-asp.html](https://gourl.io/bitcoin-api-asp.html)

API Bitcoin PHP Instruction: [https://gourl.io/bitcoin-api-asp.html](https://gourl.io/bitcoin-bitcoin-api-asp.html)

API Python, Java, Node.js, etc: [https://gourl.io/bitcoin-api-asp.html](https://gourl.io/api.html)

Wordpress Plugin: [https://wordpress.org/plugins/gourl-bitcoin-payment-gateway-paid-downloads-membership/](https://wordpress.org/plugins/gourl-bitcoin-payment-gateway-paid-downloads-membership/)

Demo: [https://gourl.io/bitcoin-payment-gateway-api.html](https://gourl.io/bitcoin-payment-gateway-api.html)



# ![Payment-Gateway](https://gourl.io/images/gateway_asp.jpg)


Instruction - ASP .NET Bitcoin/Altcoin Plugin
----------------------------------------------
* 1. Install plugin from nuget.org - https://www.nuget.org/packages/GoUrl.io/ (command "Install-Package GoUrl.io", it is plugin only without examples) 
*  or download full plugin with Examples from github / [gourl.io](https://coins.gourl.io/lib/gourl_asp.rar) directly
* 2. Plugin can use database for storing bitcoin/altcoin payment information (transaction ID, payment Date, user ID, order ID, etc) on your website. If you wish to use it you will  need to create a new MSSQL table ([crypto_payments](https://github.com/cryptoapi/Bitcoin-Payment-Gateway-ASP.NET#mssql-table-for-plugin)) and configure 'connectionStrings' in [/GoUrl/Web.config](https://github.com/cryptoapi/Bitcoin-Payment-Gateway-ASP.NET/blob/master/GoUrl/Web.config#L53). Plugin Database store in [/GoUrl/App_Data](https://github.com/cryptoapi/Bitcoin-Payment-Gateway-ASP.NET/tree/master/GoUrl/App_Data) folder. HTML Page with [Payment Table Example](https://github.com/cryptoapi/Bitcoin-Payment-Gateway-ASP.NET/blob/master/GoUrl/Views/Examples/Payments.cshtml)
* 3. [Free Register](https://gourl.io/view/registration/New_User_Registration.html) or [Login](https://gourl.io/info/memberarea/My_Account.html) on the gourl.io, [create new payment box/es](https://gourl.io/editrecord/coin_boxes/0) and get free GoUrl Private/Public Keys ([screenshot](https://gourl.io/images/paymentbox1.png))
* 4. Place all your [GoUrl Private Keys](https://gourl.io/images/paymentbox1.png) in [/GoUrl/Web.config](https://github.com/cryptoapi/Bitcoin-Payment-Gateway-ASP.NET/blob/master/GoUrl/Web.config#L15) ([screenshot](https://gourl.io/images/instruction-asp-config1.png))
* 5. Add in your _Layout  line - &lt;script type="text/javascript" src="~/scripts/cryptobox.js"&gt;&lt;/script&gt;. See example - [/GoUrl/Views/Shared/_Layout.cshtml](https://github.com/cryptoapi/Bitcoin-Payment-Gateway-ASP.NET/blob/master/GoUrl/Views/Shared/_Layout.cshtml#L8)
* 6. Create payment controller with your public/private keys, orderID, userID, etc. See example controller - [/GoUrl/Controllers/GoUrl/ExamplesController.cs](https://github.com/cryptoapi/Bitcoin-Payment-Gateway-ASP.NET/blob/master/GoUrl/Controllers/GoUrl/ExamplesController.cs#L22) ([screenshot](https://gourl.io/images/instruction-asp-config2.png))
* 7. Edit file [/GoUrl/GoUrlCore/NewPayment.cs](https://github.com/cryptoapi/Bitcoin-Payment-Gateway-ASP.NET/blob/master/GoUrl/GoUrlCore/NewPayment.cs#L9) to add additional actions after a payment has been received (update database records, send email to user, etc). 
* 8. You will need to place Callback URL in bitcoin/altcoin payment box ([screenshot](https://gourl.io/images/paymentbox6.png)), please use: http://yoursite.com/GoUrl/Callback
* 9. Run examples from [/GoUrl/Views/Examples/](https://github.com/cryptoapi/Bitcoin-Payment-Gateway-ASP.NET/tree/master/GoUrl/Views/Examples)

THAT'S IT! CRYPTOCOIN PAYMENT BOX/CAPTCHA SHOULD NOW BE WORKING ON YOUR SITE.

Read more - [https://gourl.io/bitcoin-api-asp.html](https://gourl.io/bitcoin-api-asp.html)


MSSQL Table for plugin
--------------------------
Please run query below which will create an MSSQL table where all bitcoin/altcoin payments made to you will be stored. 
You can have multiple cryptoboxes on site (such as bitcoin, dash, dogecoin/etc) and all payment information for such transactions 
will be stored in that one table.


	CREATE TABLE dbo.crypto_payments (
       paymentID int IDENTITY(1,1) NOT NULL,
       boxID int NOT NULL,
       boxType nvarchar(10) NOT NULL,
       orderID varchar(50) NOT NULL,
       userID varchar(50) NOT NULL,
       countryID varchar(3) NOT NULL,
       coinLabel varchar(6) NOT NULL,
       amount decimal(20, 8) NOT NULL,
       amountUSD decimal(20, 8) NOT NULL,
       unrecognised tinyint NOT NULL,
       addr nvarchar(50) NOT NULL,
       txID char(64) NOT NULL,
       txDate datetime NULL,
       txConfirmed tinyint NOT NULL,
       txCheckDate datetime NULL,
       processed tinyint NOT NULL,
       processedDate datetime NULL,
       recordCreated datetime NULL
	);





GoUrl Gateway Features
----------------------------

Our Payment Gateway with Instant Checkout allows you to easily organise your website -

* 100% Free Open Source on Github.com
* No Monthly Fee, Transaction Fee from 0%
* No ID Required, No Bank Account Needed
* Get payments straight to your bitcoin/altcoin wallets and convert to [USD/EUR/etc](https://gourl.io/#usd) later
* [Pay-Per-Product](http://gourl.io/lib/examples/pay-per-product-multi.php) - sell your products for bitcoin, dogecoin, litecoin, etc. online on your website. It is easy!
* [Pay-Per-Download](http://gourl.io/lib/examples/pay-per-download-multi.php) -  make money on file downloads/other digital content from your website online
* [Pay-Per-Post](http://gourl.io/lib/examples/pay-per-post-multi.php) - get separate payments for each post/article published on your website
* [Pay-Per-Registration](http://gourl.io/lib/examples/pay-per-registration-multi.php) - earn money on user registration on your website; stop spam
* [Pay-Per-Page-Access](http://gourl.io/lib/examples/pay-per-page-multi.php) - sell paid access to selected web page(es) to unregistered visitors online
* [Pay-Per-Membership](http://gourl.io/lib/examples/pay-per-membership-multi.php) - sell monthly/daily membership of your website to members online
* Set your own Prices in USD. It will automatically convert usd to cryptocoins using Live [exchange rates](https://poloniex.com/)
* Direct Integration on your website (iframe), no external payment pages opens (as other payment gateways offer)
* User will see successful payment result typically within 5 seconds after the payment has been sent
* Your website users and visitors will see GoUrl payment box on your website in their own native languages
* Our Payment Gateway supports the following interface languages: [English](https://gourl.io/bitcoin-payment-gateway-api.html?gourlcryptolang=en#gourlcryptolang), [Spanish](https://gourl.io/bitcoin-payment-gateway-api.html?gourlcryptolang=es#gourlcryptolang), [French](https://gourl.io/bitcoin-payment-gateway-api.html?gourlcryptolang=fr#gourlcryptolang), [German](https://gourl.io/bitcoin-payment-gateway-api.html?gourlcryptolang=de#gourlcryptolang), [Dutch](https://gourl.io/bitcoin-payment-gateway-api.html?gourlcryptolang=nl#gourlcryptolang), [Italian](https://gourl.io/bitcoin-payment-gateway-api.html?gourlcryptolang=it#gourlcryptolang), [Russian](https://gourl.io/bitcoin-payment-gateway-api.html?gourlcryptolang=ru#gourlcryptolang), [Polish](https://gourl.io/bitcoin-payment-gateway-api.html?gourlcryptolang=pl#gourlcryptolang), [Portuguese](https://gourl.io/bitcoin-payment-gateway-api.html?gourlcryptolang=pt#gourlcryptolang), [Persian](https://gourl.io/bitcoin-payment-gateway-api.html?gourlcryptolang=fa#gourlcryptolang), [Korean](https://gourl.io/bitcoin-payment-gateway-api.html?gourlcryptolang=ko#gourlcryptolang), [Japanese](https://gourl.io/bitcoin-payment-gateway-api.html?gourlcryptolang=ja#gourlcryptolang), [Indonesian](https://gourl.io/bitcoin-payment-gateway-api.html?gourlcryptolang=id#gourlcryptolang), [Turkish](https://gourl.io/bitcoin-payment-gateway-api.html?gourlcryptolang=tr#gourlcryptolang), [Arabic](https://gourl.io/bitcoin-payment-gateway-api.html?gourlcryptolang=ar#gourlcryptolang), [Simplified Chinese](https://gourl.io/bitcoin-payment-gateway-api.html?gourlcryptolang=cn#gourlcryptolang), [Traditional Chinese](https://gourl.io/bitcoin-payment-gateway-api.html?gourlcryptolang=zh#gourlcryptolang), [Hindi](https://gourl.io/bitcoin-payment-gateway-api.html?gourlcryptolang=hi#gourlcryptolang). We can also add any new language to payment system on [request](https://gourl.io/bitcoin-api-asp.html#lan)
* [Affiliate Program for Web Developers](https://gourl.io/affiliates.html) - Earn 0.50% Lifetime from each cryptocoin payment made by users through GoUrl Payment Gateway
* Global, Anonymous, Secure, Zero Risk, No Chargebacks, No visitor registration is needed.
* GoUrl Bitcoin Official [Wordpress Plugin](https://gourl.io/bitcoin-wordpress-plugin.html) - easy to use on your website
* [Free Support](https://gourl.io/view/contact/Contact_Us.html) in the integration of our GoUrl Crypto Payment Gateway in your scripts/plugins/website





Introduction
----------------

GoUrl Bitcoin/Altcoin Payment Gateway offer a simple ASP.NET C# Plugin which you can easily integrate into your own ASP website in minutes.

Start accepting payments on your website, including all major cryptocoins, and start selling online in minutes. No application process.

The big benefit of Cryptocoin Payment Box is that it fully integrated on your website, no external payment pages opens (as other payment gateways offer). 

Your website will receive full user payment information immediately after cryptocoin payment is made and you can process it in automatic mode.


# ![Payment-Box](https://gourl.io/images/bitcoinbox.png)



How It Works
----------------

**A. Website Owner / Seller Side**

You can use the following steps to sell your products on your website for cryptocoins if you wish to and can automatically convert them to USD

* [Install](https://gourl.io/bitcoin-api-asp.html#installation) GoUrl crypto Payment Box on your website and dynamically configure order id, currency, amount to pay, etc. Or use [Monetiser Online](https://gourl.io/view/newurl/Cryptocoin_Monetiser_Make_Money_Online.html) if you don't have your own website.
* You can accept payments in Bitcoins only or you can accept other coins - Dogecoin, Litecoin, Reddcoin, etc also. See [Demo1](http://gourl.io/lib/examples/pay-per-product-multi.php) (multiple coins) or [Demo2](http://gourl.io/lib/examples/pay-per-membership.php?gourlcryptocoin=bitcoin) (Bitcoin only)
* When you [setup](https://gourl.io/editrecord/coin_boxes/0) Cryptocoin Payment Box, you can enter the [original amount](https://gourl.io/images/instruction-config2.png) in USD or in cryptocoins. The USD amount will be automatically converted to cryptocoin amount using today's LIVE cryptocurrency exchange rates (updated every 30 minutes) and the cryptocoin amount will be displayed in the payment box. For example, if you entered 20 USD, it will display 0.059 BTC in the payment box.
* You will need to create an account on [Poloniex.com](https://poloniex.com/) or on [Bitstamp.net](https://www.bitstamp.net/) (trading platforms)
* [Setup](https://gourl.io/images/instruction-config3.png) so that all your received payments are automatically forwarded from your GoUrl.io account to your account on Poloniex / Bitstamp (enter your Poloniex/Bitstamp coin wallet address in gourl [payment box settings](https://gourl.io/images/instruction-config3.png)). And use the "autosell" feature (auto trade your cryptocoins to USD) on Poloniex/Bitstamp.
* Using that functionality you don't need to worry if cryptocurrency prices go down or up. Within 1-2 hours after a cryptocoin payment has been received by you, your payment will be automatically converted to USD on Poloniex/Bitstamp and will be kept on your Poloniex/Bitstamp USD account.
* Later you can withdraw your USD from Poloniex/Bitstamp to your own USA/UK/France/etc bank account


**B. End User / Buyer Side**

* All your users will see GoUrl [Payment Box](https://gourl.io/bitcoin-api-asp.html#live) on your webpage, and some users will use their coin wallets and make payments to you
* In around 5 seconds after cryptocoin payment is made, user will see confirmation on your website page that payment is received (i.e. very fast)
* Your website will automatically immediately receive current user id with full payment information from our payment server
* The user will still be on your webpage and see that successful payment result, your script can automatically process payment and give user confirmation (for example, upgrading user membership or giving download link on your products, etc). All in automatic mode - no manual actions are needed
* For user that payment procedure on your website will be looking very similar visually and compare with normal credit cards for its speed
* No paperwork, no chargebacks, no monthly fee, low transaction fee ([from 0%](https://gourl.io/#section4)). Please note that during the next 30 minutes (after transaction is verified) payment will be automatically forwarded to your wallet address




	
Payment API List :
---------------------

* [Bitcoin Payment API](https://gourl.io/bitcoin-payment-gateway-api.html)
* [Litecoin Payment API](https://gourl.io/litecoin-payment-gateway-api.html)
* [Paycoin Payment API](https://gourl.io/paycoin-payment-gateway-api.html)
* [Dogecoin Payment API](https://gourl.io/dogecoin-payment-gateway-api.html)
* [Dash Payment API](https://gourl.io/dash-payment-gateway-api.html)
* [Speedcoin Payment API](https://gourl.io/speedcoin-payment-gateway-api.html)
* [Reddcoin Payment API](https://gourl.io/reddcoin-payment-gateway-api.html)
* [Potcoin Payment API](https://gourl.io/potcoin-payment-gateway-api.html)
* [Feathercoin Payment API](https://gourl.io/feathercoin-payment-gateway-api.html)
* [Vertcoin Payment API](https://gourl.io/vertcoin-payment-gateway-api.html)
* [Vericoin Payment API](https://gourl.io/vericoin-payment-gateway-api.html)
* [MonetaryUnit Payment API](https://gourl.io/monetaryunit-payment-gateway-api.html)
* [Peercoin Payment API](https://gourl.io/peercoin-payment-gateway-api.html)
* [Swiscoin Payment API](https://gourl.io/swiscoin-payment-gateway-api.html)


.


PHP Examples / Live Demo :
-----------------------------

* **Pay-Per-Product**: Example1 - [multiple crypto](http://gourl.io/lib/examples/pay-per-product-multi.php), Example2 - [bitcoin](http://gourl.io/lib/examples/pay-per-product.php)
* **Pay-Per-Download**: Example3 - [multiple crypto](http://gourl.io/lib/examples/pay-per-download-multi.php), Example4 - [bitcoin](http://gourl.io/lib/examples/pay-per-download.php)
* **Pay-Per-Post**: Example5 - [multiple crypto](http://gourl.io/lib/examples/pay-per-post-multi.php), Example6 - [bitcoin](http://gourl.io/lib/examples/pay-per-post.php)
* **Pay-Per-Registration**: Example7 - [multiple crypto](http://gourl.io/lib/examples/pay-per-registration-multi.php), Example8 - [bitcoin](http://gourl.io/lib/examples/pay-per-registration.php)
* **Pay-Per-Page-Access**: Example19 - [multiple crypto](http://gourl.io/lib/examples/pay-per-page-multi.php), Example10 - [bitcoin](http://gourl.io/lib/examples/pay-per-page.php)
* **Pay-Per-Membership**: Example11 - [multiple crypto](http://gourl.io/lib/examples/pay-per-membership-multi.php), Example12 - [bitcoin](http://gourl.io/lib/examples/pay-per-membership.php)
          
            