# yahoo-node-streamer
Yahoo finance NodeJS Price Quote Live Streaming - using websocket to collect recent updates


# Install
```
npm install
```

# Run it
```
npm index.js
```

# Configuration

For example, app will subscribe to AMC and TSLA symbols. 
Check config and extend the list wit symbols you need:
```
// Extend this list by adding more symbols ["AMC", "TSLA"]
connection.send('{"subscribe":["AMC", "TSLA"]}')
```

# Received messages decoded example

```
All data set:  {
  id: 'TSLA',
  price: 600.9299926757812,
  time: Long { low: -2101540592, high: 376, unsigned: false },
  currency: '',
  exchange: 'NMS',
  quoteType: 8,
  marketHours: 0,
  changePercent: -1.6947742700576782,
  dayVolume: Long { low: 0, high: 0, unsigned: false },
  dayHigh: 0,
  dayLow: 0,
  change: -10.3599853515625,
  shortName: '',
  expireDate: Long { low: 0, high: 0, unsigned: false },
  openPrice: 0,
  previousClose: 0,
  strikePrice: 0,
  underlyingSymbol: '',
  openInterest: Long { low: 0, high: 0, unsigned: false },
  optionsType: 0,
  miniOption: Long { low: 0, high: 0, unsigned: false },
  lastSize: Long { low: 0, high: 0, unsigned: false },
  bid: 0,
  bidSize: Long { low: 0, high: 0, unsigned: false },
  ask: 0,
  askSize: Long { low: 0, high: 0, unsigned: false },
  priceHint: Long { low: 2, high: 0, unsigned: false },
  vol_24hr: Long { low: 0, high: 0, unsigned: false },
  volAllCurrencies: Long { low: 0, high: 0, unsigned: false },
  fromcurrency: '',
  lastMarket: '',
  circulatingSupply: 0,
  marketcap: 0
}
Decoded message TSLA with price: 600.9299926757812

```

# Extras

Socket.io package will be installed and app can use it to connect with another Socket.IO server where decoded data will be sent. 
That server and be used to distribute messages generated by this app (decode worker) and used in different apps: React web app, display data on your website etc.

Feature is disabled by default and can be enabled in:

```
// Line 18
var useSocket = false;
```

Remember to configuer connection to socket server before enabling it. 
