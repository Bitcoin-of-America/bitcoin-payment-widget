# bitcoin-payment-widget
Accept cryptocoin payments on any website with a few lines of code. Powered by BitcoinOfAmerica.org

## Quick Start

Insert the following code right before your closing <body> tag:
```
<script>
   bcoa_options = {
      merchantid: "MERCHANTID",
      confirmations: 3,
      notifyurl: "",
      cancel: function() { },
      complete: function() { }
   }
</script>   
<script src="bcoa-widget.php"></script>
```
  
Then use the following code to create a payment button to open a widget:

```
<button 
    data-price-cents="199" 
    data-price-crypto="0"
    data-product-id="123"
    data-invoice-id="456"
    data-customer-id="789"
    data-description="Product Name"
    data-coin-type="btc" 
>Pay Now!</button>
```

## Configurable Options

- **merchantid** - Your BitcoinOfAmerica merchant identifier. Can be obtained by signing up for free as a merchant at [bitcoinOfAmerica](https://www.bitcoinofamerica.org)
- **confirmations** - The number of blockchain confirmations required before widget displays an "order complete" message, and calls the optional *complete* callback. 
- **notifyurl** - This optional URL on your server will be notified each time a confirmation is received. Only the the first 6 payment confirmations will be handled {see **Notification URL** below}.
- **complete** - Callback function. Called when all required confirmations have been received for payment.
- **cancel** - Callback function. Called if customer closes the widget before receiving a payment receiving address.

## Button Options

- **data-coin-type** - Coin type for payment. Must be one of BTC, LTC, BCH, ECH, or XRP.
- **date-price-cents** - The price of the product or service that you're selling, in pennies. Set to 0 if your price is in satoshi units (crypto) instead of fiat.
- **data-price-crypto** - The price of the product or service that you're selling in crypto units {see **Coin Specific Units** below}.  If your price is in satoshi units (crypto) instead of fiat, set this to 0.
- **data-description** - The product or service your customer is buying. This is displayed to your customer in the widget. 
- **data-product-id** - Optional pass-thru value.
- **data-invoice-id** - Optional pass-thru value.
- **data-customer-id** - Optional pass-thru value.


## Coin Specific Units

```
1 BTC (Bitcoin)      = 100,000,000 (1e8) satoshi
1 LTC (Litecoin)     = 100,000,000 (1e8) photons
1 BCH (Bitcoin Cash) = 100,000,000 (1x8) satoshi
1 ETH (Ethereum)     = 1,000,000,000,000,000,000 wei
1 XRP (Ripple)       = 1,000,000 (1e6) drops
```
      
