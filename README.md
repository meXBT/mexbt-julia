# mexbt-julia
Julia client library for the meXBT API Exchange

[![Build Status](https://travis-ci.org/Ahimta/mexbt-julia.svg?branch=master)](https://travis-ci.org/Ahimta/mexbt-julia)

## Usage

```julia
Pkg.add("MexbtClient")
using MexbtClient

ticker("BTCMXN")["isAccepted"]
trades("BTCMXN")["isAccepted"]
tradesByDate("BTCMXN", 1416530012, 1416559390)["isAccepted"]
orderBook("BTCMXN")["isAccepted"]
productPairs()["isAccepted"]

account = Account("4b0911e93f372a401456061a70e4299a", "1831845ddae9cf45e57b851ff2ca0117", "ahimta@outlook.com", true)
order = createOrder(account, "BTCUSD", "buy", 0, 1.0, 342.99)
order["isAccepted"]
createMarketOrder(account, "BTCUSD", "buy", 1.0, 342.99)["isAccepted"]
createLimitOrder(account, "BTCUSD", "buy", 1.0, 342.99)["isAccepted"]
modifyOrder(account, "BTCUSD", order["serverOrderId"], 0)["isAccepted"]
moveOrderToTop(account, "BTCUSD", order["serverOrderId"])["isAccepted"]
executeOrder(account, "BTCUSD", order["serverOrderId"])["isAccepted"]
cancelOrder(account, "BTCUSD", order["serverOrderId"])["isAccepted"]
cancelAllOrders(account, "BTCUSD")["isAccepted"]
accountInfo(account)["isAccepted"]
balance(account)["isAccepted"]
accountTrades(account, "BTCUSD")["isAccepted"]
orders(account)["isAccepted"]
depositAddresses(account)["isAccepted"]
depositAddresses(account, "BTC")["isAccepted"]
withdraw(account, "BTC", 1.2345678, "1yL8LFT5qqzPJY3hMRQCJd5CTs2F7SHjv")["isAccepted"]
```
