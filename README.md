# bitcoin-payment-widget
Accept cryptocoin payments on any website with a few lines of code. Powered by BitcoinOfAmerica.org

## Quick Start

Insert the following code right before your closing <body> tag:
```
bcoa_options = {
   merchantid: "MERCHANTID",
   customerid: "",
   confirmations: 3,
   notifyurl: "",
   cancel: function() { },
   complete: function() { }
}
<script src="bcoa-widget.php"></script>
```
  
Then use the following code to create a payment button to open a widget:

```
<button 
    data-price-cents="199" 
    data-price-crypto="0"
    data-product-id="123"
    data-description="Product Name"
    data-coin-type="btc" 
>Pay Now!</button>
```

## Configurable Options

- **merchantid** - Your BitcoinOfAmerica merchant identifier. Can be obtained by signing up for free as a merchant on [bitcoinOfAmerica](https://www.bitcoinofamerica.org)
- **price_cents** - The price of the product or service that you're selling in pennies. Set to 0 if your price is in satoshi units (crypto) instead of fiat.
- **price_crypto** - The price of the product or service that you're selling in crypto units {see **Coin Specific Units** below}.  Set to 0 if your price is in satoshi units (crypto) instead of fiat.
- **confirmations** - The number of confirmations required before widget displays order complete message and calls the optional *complete* callback. 
- **notifyurl** - This URL on your server will be notified with the first 6 payment confirmations only {see **Notification URL** below}.
- **customerid** - Optional passthru value
- **invoiceid** - Optional passthru value
- **cancel** - Callback function. Called if customer closes the widget before receiving a payment receiving address.


## Coin Specific Units

```
1 BTC (Bitcoin)      = 100,000,000 (1e8) satoshi
1 LTC (Litecoin)     = 100,000,000 (1e8) photons
1 BCH (Bitcoin Cash) = 100,000,000 (1x8) satoshi
1 ETH (Ethereum)     = 1,000,000,000,000,000,000 wei
1 XRP (Ripple)       = 1,000,000 (1e6) drops
```
      
