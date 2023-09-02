{
  "version": 7,
  "createdAt": 1687519872651,
  "updatedAt": 1692268461710,
  "name": "Liquidity with Multi CVD",
  "id": "gv8h",
  "states": {
    "panes": {
      "_id": "panes",
      "locked": false,
      "panes": {
        "chart": {
          "id": "chart",
          "name": "",
          "type": "chart",
          "markets": [
            "BINANCE_FUTURES:btcusd_perp",
            "BITFINEX:BTCUSD",
            "BITMEX:XBTUSD",
            "BYBIT:BTCUSD",
            "COINBASE:BTC-USD",
            "DERIBIT:BTC-PERPETUAL",
            "BINANCE:btcusdt",
            "BINANCE_FUTURES:btcusdt",
            "BINANCE:btcbusd",
            "BINANCE_FUTURES:btcbusd",
            "BITGET:BTCUSDT",
            "BITGET:BTCUSDT_UMCBL",
            "BITFINEX:BTCUST",
            "BITFINEX:BTCF0:USTF0",
            "BITMEX:XBTUSDT",
            "BYBIT:BTCUSDT",
            "COINBASE:BTC-USDT",
            "BITSTAMP:btcusd",
            "KRAKEN:PI_XBTUSD",
            "OKEX:BTC-USD-SWAP",
            "OKEX:BTC-USDT-SWAP"
          ]
        },
        "trades": {
          "id": "trades",
          "name": "",
          "type": "trades",
          "markets": [
            "BINANCE_FUTURES:btcusd_perp",
            "BITFINEX:BTCUSD",
            "BITMEX:XBTUSD",
            "BYBIT:BTCUSD",
            "COINBASE:BTC-USD",
            "DERIBIT:BTC-PERPETUAL",
            "BINANCE:btcusdt",
            "BINANCE_FUTURES:btcusdt",
            "BINANCE:btcbusd",
            "BINANCE_FUTURES:btcbusd",
            "BITGET:BTCUSDT",
            "BITGET:BTCUSDT_UMCBL",
            "BITFINEX:BTCUST",
            "BITFINEX:BTCF0:USTF0",
            "BITMEX:XBTUSDT",
            "BYBIT:BTCUSDT",
            "COINBASE:BTC-USDT",
            "BITSTAMP:btcusd",
            "KRAKEN:PI_XBTUSD",
            "OKEX:BTC-USD-SWAP",
            "OKEX:BTC-USDT-SWAP"
          ],
          "settings": {
            "showLiquidations": false
          }
        },
        "liquidations": {
          "id": "liquidations",
          "name": "REKTS",
          "type": "trades",
          "markets": [
            "BITFINEX:BTCUSD",
            "BITMEX:XBTUSD",
            "BITMEX:XBTUSDT",
            "BITFINEX:BTCF0:USTF0",
            "BINANCE_FUTURES:btcusdt",
            "BINANCE_FUTURES:btcbusd",
            "BINANCE_FUTURES:btcusd_perp",
            "DERIBIT:BTC-PERPETUAL",
            "BYBIT:BTCUSD",
            "BYBIT:BTCUSDT",
            "KRAKEN:PI_XBTUSD",
            "OKEX:BTC-USD-SWAP",
            "OKEX:BTC-USDT-SWAP"
          ],
          "settings": {
            "showTrades": false
          }
        }
      },
      "layout": [
        {
          "i": "chart",
          "type": "chart",
          "x": 0,
          "y": 0,
          "w": 23,
          "h": 22,
          "moved": false
        },
        {
          "i": "trades",
          "type": "trades",
          "x": 10,
          "y": 22,
          "w": 10,
          "h": 23,
          "moved": false
        },
        {
          "i": "liquidations",
          "type": "trades",
          "x": 0,
          "y": 22,
          "w": 10,
          "h": 23,
          "moved": false
        }
      ]
    },
    "chart": {
      "indicatorsErrors": {},
      "indicators": {
        "cvd": {
          "enabled": true,
          "name": "CVD",
          "description": "Cumulative Volume Delta",
          "script": "plotline(cum(vbuy - vsell))",
          "options": {
            "priceScaleId": "cvd",
            "priceFormat": {
              "type": "volume"
            },
            "color": "#3BCA6D",
            "scaleMargins": {
              "top": 0.84,
              "bottom": 0
            }
          },
          "id": "cvd",
          "createdAt": 1687519872502,
          "updatedAt": null,
          "series": [
            "cvd"
          ]
        },
        "liquidations": {
          "enabled": true,
          "name": "Liquidations",
          "description": "Liquidations by side",
          "script": "plothistogram(lbuy, color=options.upColor)\nplothistogram(-lsell, color=options.downColor)",
          "options": {
            "priceFormat": {
              "type": "volume"
            },
            "priceScaleId": "volume_liquidations",
            "upColor": "rgb(255,76,243)",
            "downColor": "rgb(255,183,77)",
            "scaleMargins": {
              "top": 0.75,
              "bottom": 0.17
            },
            "visible": true
          },
          "id": "liquidations",
          "createdAt": 1687519872502,
          "updatedAt": null,
          "series": [
            "liquidations",
            "vjo0gy0o"
          ]
        },
        "price": {
          "enabled": true,
          "name": "Price",
          "script": "plotcandlestick(options.useHeikinAshi ? avg_heikinashi(bar) : options.useGaps ? avg_ohlc_with_gaps(bar) : avg_ohlc(bar))",
          "options": {
            "priceScaleId": "right",
            "priceFormat": {
              "auto": true,
              "precision": 1,
              "minMove": 0.1
            },
            "priceLineVisible": true,
            "lastValueVisible": true,
            "borderVisible": true,
            "upColor": "rgb(59,202,109)",
            "downColor": "rgb(214,40,40)",
            "borderUpColor": "rgb(59,202,109)",
            "borderDownColor": "rgb(239,67,82)",
            "wickUpColor": "rgb(223,211,144)",
            "wickDownColor": "rgb(239,67,82)",
            "useGaps": false,
            "useHeikinAshi": false,
            "scaleMargins": {
              "top": 0.04,
              "bottom": 0.26
            },
            "visible": true
          },
          "id": "price",
          "createdAt": 1687519872502,
          "updatedAt": null,
          "series": [
            "price"
          ],
          "unsavedChanges": true
        },
        "volume": {
          "enabled": true,
          "name": "Volume",
          "description": "Volume + delta",
          "script": "if (upColor === 0) {\n  if (options.showDelta) {\n    upColor = options.upBgColor\n    downColor = options.downBgColor\n  } else {\n    upColor = options.upColor\n    downColor = options.downColor\n  }\n}\n\nif (options.showDelta) {\n  plothistogram({ time: time, value: Math.abs(vbuy-vsell), color: vbuy - vsell > 0 ? options.upColor : options.downColor})\n}\n\nplothistogram({ time: time, value: vbuy + vsell, color: vbuy > vsell ? upColor : downColor })",
          "options": {
            "priceFormat": {
              "type": "volume"
            },
            "upColor": "rgb(59,202,109)",
            "downColor": "rgb(235,30,47)",
            "priceScaleId": "volume",
            "scaleMargins": {
              "top": 0.84,
              "bottom": 0
            },
            "showDelta": true,
            "upBgColor": "rgba(59,202,109,0.5)",
            "downBgColor": "rgba(235,30,47,0.5)",
            "visible": true
          },
          "id": "volume",
          "createdAt": 1687519872502,
          "updatedAt": null,
          "series": [
            "volume",
            "xr96j7ba"
          ]
        },
        "multi-cvd-perp": {
          "script": "plotline(cum((BITGET:BTCUSDT_UMCBL.vbuy)-(BITGET:BTCUSDT_UMCBL.vsell)), title=Bitget.perp, color=\"aqua\")\nplotline(cum((BINANCE_FUTURES:btcusd_perp.vbuy)-(BINANCE_FUTURES:btcusd_perp.vsell)), title=Binance.perp, color=\"red\")\nplotline(cum((BITFINEX:BTCF0:USTF0.vbuy)-(BITFINEX:BTCF0:USTF0.vsell)), title=BITFINEX.perp, color=\"purple\")\nplotline(cum((BITMEX:XBTUSD.vbuy)-(BITMEX:XBTUSD.vsell)), title=BITMEX.perp, color=\"pink\")\nplotline(cum((BYBIT:BTCUSD.vbuy+BYBIT:BTCUSDT.vbuy)-(BYBIT:BTCUSD.vsell+BYBIT:BTCUSDT.vsell)), title=BYBIT.perp, color=\"orange\")\nplotline(cum((DERIBIT:BTC-PERPETUAL.vbuy)-(DERIBIT:BTC-PERPETUAL.vsell)), title=DERIBIT.perp, color=\"silver\")\n//plotline(cum((FTX:BTC-PERP.vbuy)-(FTX:BTC-PERP.vsell)), title=FTX.perp, color=\"apricot\")\nplotline(cum((HUOBI:BTC-USD.vbuy)-(HUOBI:BTC-USD.vsell)), title=HUOBI.perp,color=\"yellow\")\nplotline(cum((KRAKEN:PI_XBTUSD.vbuy)-(KRAKEN:PI_XBTUSD.vsell)), title=HUOBI.perp,color=\"blue\")\nplotline(cum((OKEX:BTC-USDT-SWAP.vbuy+OKEX:BTC-USD-SWAP.vbuy)-(OKEX:BTC-USDT-SWAP.vsell+OKEX:BTC-USD-SWAP.vsell)), title=OKEX.perp, color=\"white\")",
          "name": " Multi CVD (PERP)",
          "options": {
            "priceScaleId": "right",
            "visible": false,
            "scaleMargins": {
              "top": 0.04,
              "bottom": 0.26
            }
          },
          "id": "multi-cvd-perp",
          "priceScaleId": "right",
          "series": [
            "multi-cvd-perp",
            "bk3lo6c5",
            "p3vvpp65",
            "8d9mlfr1",
            "70gwy1v1",
            "l2lxka8p",
            "e5x8yc1w",
            "qredtdow",
            "os4faqkk"
          ],
          "displayName": " Multi CVD (PERP)",
          "unsavedChanges": false
        },
        "multi-cvd-spot": {
          "script": "plotline(cum((BITGET:BTCUSDT.vbuy)-(BITGET:BTCUSDT.vsell)), title=Bitget.spot, color=\"aqua\")\nplotline(cum((BINANCE:btcusdt.vbuy+BINANCE:btcusdc.vbuy)-(BINANCE:btcusdt.vsell+BINANCE:btcusdc.vsell)), title=Binance.spot, color=\"red\")\nplotline(cum((BITFINEX:BTCUSD.vbuy)-(BITFINEX:BTCUSD.vsell)), title=BITFINEX.spot, color=\"purple\")\nplotline(cum((BITSTAMP:btcusd.vbuy+BITSTAMP:btcusdt.vbuy)-(BITSTAMP:btcusd.vsell+BITSTAMP:btcusdt.vsell)), title=BITSTAMP.spot, color=\"green\")\nplotline(cum((COINBASE:BTC-USDC.vbuy+COINBASE:BTC-USD.vbuy+COINBASE:BTC-USDT.vbuy)-(COINBASE:BTC-USDC.vsell+COINBASE:BTC-USD.vsell+COINBASE:BTC-USDT.vsell)), title=COINBASE.spot,color=\"orange\")\nplotline(cum((HUOBI:btcusdc.vbuy)-(HUOBI:btcusdc.vsell)), title=HUOBI.spot,color=\"yellow\")\nplotline(cum((KRAKEN:XBT/USDC.vbuy+KRAKEN:XBT/USDT.vbuy+KRAKEN:XBT/USD.vbuy)-(KRAKEN:XBT/USDC.vsell+KRAKEN:XBT/USDT.vsell+KRAKEN:XBT/USD.vsell)), title=Kraken.spot,color=\"blue\")\n//plotline(cum((OKEX:BTC-USDT.vbuy+OKEX:BTC-USDC.vbuy)-(OKEX:BTC-USDT.vsell+OKEX:BTC-USDC.vsell)), title=OKEX.spot, color=\"white\")\nplotline(cum((POLONIEX:BTC_USDT.vbuy+POLONIEX:USDC_BTC.vbuy)-(POLONIEX:BTC_USDT.vsell+POLONIEX:USDC_BTC.vsell)), title=POLONIEX.spot,color=\"silver\")",
          "name": " Multi CVD (SPOT)",
          "options": {
            "priceScaleId": "btcmultispot",
            "priceFormat": {
              "type": "volume"
            },
            "scaleMargins": {
              "top": 0.1,
              "bottom": 0.2
            },
            "visible": true
          },
          "id": "multi-cvd-spot",
          "priceScaleId": "right",
          "series": [
            "multi-cvd-spot",
            "65e5494m",
            "4srw492u",
            "k6lpl3bw",
            "a4gtz5ab",
            "ix4vp216",
            "wvo37vwo",
            "i527acil"
          ],
          "displayName": " Multi CVD (SPOT)",
          "unsavedChanges": true
        },
        "btccvdperp": {
          "script": "line(cum((BITGET:BTCUSDT_UMCBL.vbuy+BINANCE_FUTURES:btcusdt.vbuy+BINANCE_FUTURES:btcusd_perp.vbuy+BITFINEX:BTCF0:USTF0.vbuy+BITMEX:XBTUSD.vbuy+BYBIT:BTCUSD.vbuy+BYBIT:BTCUSDT.vbuy+DERIBIT:BTC-PERPETUAL.vbuy+FTX:BTC-PERP.vbuy+HUOBI:BTC-USD.vbuy+KRAKEN:PI_XBTUSD.vbuy+OKEX:BTC-USDT-SWAP.vbuy+OKEX:BTC-USD-SWAP.vbuy)- (BITGET:BTCUSDT_UMCBL.vsell+BINANCE_FUTURES:btcusdt.vsell+BINANCE_FUTURES:btcusd_perp.vsell+BITFINEX:BTCF0:USTF0.vsell+BITMEX:XBTUSD.vsell+BYBIT:BTCUSD.vsell+BYBIT:BTCUSDT.vsell+DERIBIT:BTC-PERPETUAL.vsell+FTX:BTC-PERP.vsell+HUOBI:BTC-USD.vsell+KRAKEN:PI_XBTUSD.vsell+OKEX:BTC-USDT-SWAP.vsell+OKEX:BTC-USD-SWAP.vsell)), title=CVD:BTC:PERP)",
          "name": "CVD (BTC PERP)",
          "description": "CVD specific markets",
          "options": {
            "priceScaleId": "cvdperp",
            "priceFormat": {
              "type": "volume"
            },
            "color": "#42a5f5",
            "scaleMargins": {
              "top": 0.1,
              "bottom": 0.2
            },
            "visible": false
          },
          "id": "btccvdperp",
          "createdAt": 1687519872502,
          "updatedAt": 1623024000000,
          "series": [
            "btccvdperp"
          ],
          "displayName": "CVD (BTC PERP)"
        },
        "btccvdspot": {
          "script": "line(cum((BITGET:BTCUSDT.vbuy+BINANCE:btcusdt.vbuy+BINANCE:btcusdc.vbuy+BITFINEX:BTCUSD.vbuy+BITSTAMP:btcusd.vbuy+BITSTAMP:btcusdt.vbuy+BITSTAMP:btcusdc.vbuy+COINBASE:BTC-USDC.vbuy+COINBASE:BTC-USD.vbuy+COINBASE:BTC-USDT.vbuy+FTX:BTC/USD.vbuy+FTX:BTC/USDT.vbuy+HUOBI:btcusdt.vbuy+HUOBI:btcusdc.vbuy+KRAKEN:XBT/USDC.vbuy+KRAKEN:XBT/USDT.vbuy+KRAKEN:XBT/USD.vbuy+OKEX:BTC-USDT.vbuy+OKEX:BTC-USDC.vbuy+POLONIEX:BTC_USDT.vbuy+POLONIEX:USDC_BTC.vbuy)-(BITGET:BTCUSDT.vsell+BINANCE:btcusdt.vsell+BINANCE:btcusdc.vsell+BITFINEX:BTCUSD.vsell+BITSTAMP:btcusd.vsell+BITSTAMP:btcusdt.vsell+BITSTAMP:btcusdc.vsell+COINBASE:BTC-USDC.vsell+COINBASE:BTC-USD.vsell+COINBASE:BTC-USDT.vsell+FTX:BTC/USD.vsell+FTX:BTC/USDT.vsell+HUOBI:btcusdt.vsell+HUOBI:btcusdc.vsell+KRAKEN:XBT/USDC.vsell+KRAKEN:XBT/USDT.vsell+KRAKEN:XBT/USD.vsell+OKEX:BTC-USDT.vsell+OKEX:BTC-USDC.vsell+POLONIEX:BTC_USDT.vsell+POLONIEX:USDC_BTC.vsell)), title=CVD:BTC:SPOT)",
          "name": "CVD (BTC SPOT)",
          "description": "CVD specific markets",
          "options": {
            "priceScaleId": "cvdspot",
            "priceFormat": {
              "type": "volume"
            },
            "color": "#4caf50",
            "scaleMargins": {
              "top": 0.1,
              "bottom": 0.2
            },
            "visible": false
          },
          "id": "btccvdspot",
          "createdAt": 1687519872502,
          "updatedAt": 1623024000000,
          "series": [
            "btccvdspot"
          ],
          "displayName": "CVD (BTC SPOT)"
        },
        "liquidity-poc": {
          "script": "/* eslint-disable */\r\n// <STARTUP SCRIPT> \r\nif (!pendingMarkers) {\r\n  // runs only once\r\n  markers = []\r\n  pendingMarkers = []\r\n  lastIndex = null\r\n  freeSlots = []\r\n  usedSlots = []\r\n  drawQueue = []\r\n  boundaries = {}\r\n  intervals = {}\r\n  groups = []\r\n  liquidityAtPrices = {}\r\n  resistances = []\r\n  supports = []\r\n  pendingRedraws = []\r\n  leverages = options.leverages.toString().split(',').sort((a, b) => b - a)\r\n  buyColor = options.buyColor.match(/\\(([\\d.]+),([\\d.]+),([\\d.]+),?([\\d.]+)?\\)$/).slice(1,5).map(a => +a)\r\n  sellColor = options.sellColor.match(/\\(([\\d.]+),([\\d.]+),([\\d.]+),?([\\d.]+)?\\)$/).slice(1,5).map(a => +a)\r\n  buyOpacity = buyColor.pop()\r\n  sellOpacity = sellColor.pop()\r\n  for (var i = 1; i < series.length; i++) {\r\n    if (series[i].seriesType() !== 'BrokenArea') {\r\n      continue\r\n    }\r\n\r\n    if (i > 0) {\r\n      freeSlots.push({\r\n        index: i,\r\n        redrawAt: 0\r\n      })\r\n    }\r\n\r\n    series[i].setExtensionsBoundaries(boundaries)\r\n  }\r\n}\r\n// </STARTUP SCRIPT> \r\n\r\n// <MARKERS.UTILS> \r\nif (pendingMarkers.length) {\r\n  markers = markers.concat(pendingMarkers)\r\n  if (series[0].setMarkers) {\r\n    series[0].setMarkers(markers)\r\n  }\r\n  pendingMarkers = []\r\n}\r\n// </MARKERS.UTILS>\r\n\r\n// process only on new candle\r\nif (bar.length === lastIndex) {\r\n  return\r\n}\r\n\r\nprice = avg_heikinashi(bar)\r\nclose = price.close\r\nline(price.close, color=\"transparent\") // ghost price for markers\r\n\r\nvar ohlc4 = (price.open + price.high + price.low + price.close) / 4\r\nvar buyVolume = vbuy\r\nvar sellVolume = vsell\r\nvar avgBuyVolume = sma(buyVolume, options.length)\r\nvar avgSellVolume = sma(sellVolume, options.length)\r\nvar buyStrength = (options.log ? Math.log(1 + buyVolume / avgBuyVolume * options.logScale) : buyVolume / avgBuyVolume)\r\nvar sellStrength = (options.log ? Math.log(1 + sellVolume / avgSellVolume * options.logScale) : sellVolume / avgSellVolume)\r\n\r\nvar src = price.high\r\nfor (let i = 0; i < leverages.length; i++) {\r\n  var levMedian = Math.ceil((src + src * -(100 / (leverages)[i] / 100)) / options.step) * options.step\r\n  \r\n  if (!liquidityAtPrices[levMedian]) {\r\n    var top = levMedian + options.step / 2\r\n    var bottom = levMedian - options.step / 2\r\n    liquidityAtPrices[levMedian] = {\r\n      strength: 0,\r\n      count: 0,\r\n      top: top,\r\n      bottom: bottom\r\n    }\r\n    supports.push(levMedian)\r\n    supports.sort((a, b) => b - a)\r\n  }\r\n  \r\n  liquidityAtPrices[levMedian].count++\r\n  liquidityAtPrices[levMedian].strength = liquidityAtPrices[levMedian].strength + buyStrength\r\n  const alpha = Math.max(options.minAlpha, Math.min(1, liquidityAtPrices[levMedian].strength * liquidityAtPrices[levMedian].count * options.opacity * (buyOpacity || 1)))\r\n  liquidityAtPrices[levMedian].color = 'rgba(' + buyColor.join(',') + ',' + alpha + ')'\r\n\r\n  if (liquidityAtPrices[levMedian].strength > options.threshold) {\r\n    \r\n    if (pendingRedraws.indexOf(levMedian) === -1) {\r\n      pendingRedraws.push(levMedian)\r\n    }\r\n  }\r\n}\r\n\r\nvar src = price.low\r\nfor (let i = 0; i < leverages.length; i++) {\r\n  var levMedian = Math.ceil((src + src * (100 / (leverages)[i] / 100)) / options.step) * options.step\r\n  \r\n  if (!liquidityAtPrices[levMedian]) {\r\n    var top = levMedian + options.step / 2\r\n    var bottom = levMedian - options.step / 2\r\n    liquidityAtPrices[levMedian] = {\r\n      strength: 0,\r\n      count: 0,\r\n      top: top,\r\n      bottom: bottom\r\n    }\r\n    resistances.push(levMedian)\r\n    resistances.sort((a, b) => a - b)\r\n  }\r\n\r\n  liquidityAtPrices[levMedian].count++\r\n  liquidityAtPrices[levMedian].strength = liquidityAtPrices[levMedian].strength + buyStrength\r\n  const alpha = Math.max(options.minAlpha, Math.min(1, liquidityAtPrices[levMedian].strength * liquidityAtPrices[levMedian].count * options.opacity * (sellOpacity || 1)))\r\n  liquidityAtPrices[levMedian].color = 'rgba(' + sellColor.join(',') + ',' + alpha + ')'\r\n  if (liquidityAtPrices[levMedian].strength > options.threshold) {\r\n    if (pendingRedraws.indexOf(levMedian) === -1) {\r\n      pendingRedraws.push(levMedian)\r\n    }\r\n  }\r\n}\r\n\r\nif (pendingRedraws.length) {\r\n  \r\n  var releaseImmediately = []\r\n  for (var i = 0; i < pendingRedraws.length; i++) {\r\n    var cell = liquidityAtPrices[pendingRedraws[i]]\r\n    var slot = freeSlots.find(slot => slot.redrawAt <= bar.length)\r\n    if (slot) {\r\n      var indexFree = freeSlots[freeSlots.indexOf(slot)].index\r\n      var usedIndex = freeSlots.splice(freeSlots.indexOf(slot), 1)[0].index\r\n      usedSlots.push(usedIndex)\r\n\r\n      if (cell.id) {\r\n        boundaries[cell.id] = bar.length - 1\r\n      }\r\n\r\n      cell.id = Math.random().toString()\r\n      renderer.indicators[indicatorId].series[usedIndex] ={\r\n        id: cell.id,\r\n        time: time,\r\n        lowerValue: cell.top,\r\n        higherValue: cell.bottom,\r\n        extendRight: true,\r\n        color: cell.color\r\n      }\r\n\r\n      pendingRedraws.splice(i--, 1)\r\n      releaseImmediately.push(usedIndex)\r\n    }\r\n  }\r\n  for (let i = 0; i < releaseImmediately.length; i++) {\r\n    var plotIndexToFree = usedSlots.splice(usedSlots.indexOf(releaseImmediately[i]), 1)[0]\r\n    \r\n    freeSlots.push({\r\n      index: plotIndexToFree,\r\n      redrawAt: bar.length\r\n    })\r\n  }\r\n}\r\n\r\nfor (let i = 0; i < supports.length; i++) {\r\n  if (\r\n   price.low <= supports[i]\r\n  ) {\r\n    boundaries[liquidityAtPrices[supports[i]].id] = bar.length\r\n    delete liquidityAtPrices[supports[i]]\r\n    supports.splice(i--, 1)\r\n  } else {\r\n    break;\r\n  }\r\n}\r\n\r\nfor (let i = 0; i < resistances.length; i++) {\r\n  if (\r\n   price.high >= resistances[i]\r\n  ) {\r\n    boundaries[liquidityAtPrices[resistances[i]].id] = bar.length\r\n    delete liquidityAtPrices[resistances[i]]\r\n    resistances.splice(i--, 1)\r\n  } else {\r\n    break;\r\n  }\r\n}\r\n\r\n// set reference to bar index : avoid process next tick\r\nlastIndex = bar.length\r\n\r\nif (renderer.indicators[indicatorId].series[1]) {\r\n  brokenarea(renderer.indicators[indicatorId].series[1] || { time: time }, strokeColor=options.strokeColor, strokeWidth=options.strokeWidth)\r\n}\r\nif (renderer.indicators[indicatorId].series[2]) {\r\n  brokenarea(renderer.indicators[indicatorId].series[2] || { time: time }, strokeColor=options.strokeColor, strokeWidth=options.strokeWidth)\r\n}\r\nif (renderer.indicators[indicatorId].series[3]) {\r\n  brokenarea(renderer.indicators[indicatorId].series[3] || { time: time }, strokeColor=options.strokeColor, strokeWidth=options.strokeWidth)\r\n}\r\nif (renderer.indicators[indicatorId].series[4]) {\r\n  brokenarea(renderer.indicators[indicatorId].series[4] || { time: time }, strokeColor=options.strokeColor, strokeWidth=options.strokeWidth)\r\n}\r\nif (renderer.indicators[indicatorId].series[5]) {\r\n  brokenarea(renderer.indicators[indicatorId].series[5] || { time: time }, strokeColor=options.strokeColor, strokeWidth=options.strokeWidth)\r\n}\r\nif (renderer.indicators[indicatorId].series[6]) {\r\n  brokenarea(renderer.indicators[indicatorId].series[6] || { time: time }, strokeColor=options.strokeColor, strokeWidth=options.strokeWidth)\r\n}\r\nif (renderer.indicators[indicatorId].series[7]) {\r\n  brokenarea(renderer.indicators[indicatorId].series[7] || { time: time }, strokeColor=options.strokeColor, strokeWidth=options.strokeWidth)\r\n}\r\nif (renderer.indicators[indicatorId].series[8]) {\r\n  brokenarea(renderer.indicators[indicatorId].series[8] || { time: time }, strokeColor=options.strokeColor, strokeWidth=options.strokeWidth)\r\n}\r\nif (renderer.indicators[indicatorId].series[9]) {\r\n  brokenarea(renderer.indicators[indicatorId].series[9] || { time: time }, strokeColor=options.strokeColor, strokeWidth=options.strokeWidth)\r\n}\r\nif (renderer.indicators[indicatorId].series[10]) {\r\n  brokenarea(renderer.indicators[indicatorId].series[10] || { time: time }, strokeColor=options.strokeColor, strokeWidth=options.strokeWidth)\r\n}\r\nif (renderer.indicators[indicatorId].series[11]) {\r\n  brokenarea(renderer.indicators[indicatorId].series[11] || { time: time }, strokeColor=options.strokeColor, strokeWidth=options.strokeWidth)\r\n}\r\nif (renderer.indicators[indicatorId].series[12]) {\r\n  brokenarea(renderer.indicators[indicatorId].series[12] || { time: time }, strokeColor=options.strokeColor, strokeWidth=options.strokeWidth)\r\n}\r\nif (renderer.indicators[indicatorId].series[13]) {\r\n  brokenarea(renderer.indicators[indicatorId].series[13] || { time: time }, strokeColor=options.strokeColor, strokeWidth=options.strokeWidth)\r\n}\r\nif (renderer.indicators[indicatorId].series[14]) {\r\n  brokenarea(renderer.indicators[indicatorId].series[14] || { time: time }, strokeColor=options.strokeColor, strokeWidth=options.strokeWidth)\r\n}\r\nif (renderer.indicators[indicatorId].series[15]) {\r\n  brokenarea(renderer.indicators[indicatorId].series[15] || { time: time }, strokeColor=options.strokeColor, strokeWidth=options.strokeWidth)\r\n}\r\nif (renderer.indicators[indicatorId].series[16]) {\r\n  brokenarea(renderer.indicators[indicatorId].series[16] || { time: time }, strokeColor=options.strokeColor, strokeWidth=options.strokeWidth)\r\n}\r\nif (renderer.indicators[indicatorId].series[17]) {\r\n  brokenarea(renderer.indicators[indicatorId].series[17] || { time: time }, strokeColor=options.strokeColor, strokeWidth=options.strokeWidth)\r\n}\r\nif (renderer.indicators[indicatorId].series[18]) {\r\n  brokenarea(renderer.indicators[indicatorId].series[18] || { time: time }, strokeColor=options.strokeColor, strokeWidth=options.strokeWidth)\r\n}\r\nif (renderer.indicators[indicatorId].series[19]) {\r\n  brokenarea(renderer.indicators[indicatorId].series[19] || { time: time }, strokeColor=options.strokeColor, strokeWidth=options.strokeWidth)\r\n}\r\nif (renderer.indicators[indicatorId].series[20]) {\r\n  brokenarea(renderer.indicators[indicatorId].series[20] || { time: time }, strokeColor=options.strokeColor, strokeWidth=options.strokeWidth)\r\n}\r\nif (renderer.indicators[indicatorId].series[21]) {\r\n  brokenarea(renderer.indicators[indicatorId].series[21] || { time: time }, strokeColor=options.strokeColor, strokeWidth=options.strokeWidth)\r\n}\r\nif (renderer.indicators[indicatorId].series[22]) {\r\n  brokenarea(renderer.indicators[indicatorId].series[22] || { time: time }, strokeColor=options.strokeColor, strokeWidth=options.strokeWidth)\r\n}\r\n//line(avgvbuy * options.threshold, priceScaleId='overlay', scaleMargins={top: 0.7, bottom: 0.1}, title=\"refbuy\", color=white)\r\n//line(refVolBuy * options.threshold, priceScaleId='overlay', scaleMargins={top: 0.7, bottom: 0.1}, title=\"refsell\", color=lime)\r\n//line(vsell, priceScaleId='overlay', scaleMargins={top: 0.7, bottom: 0.1}, title=\"vsell\", color=white)\r\n//line(refVolSell, priceScaleId='overlay', scaleMargins={top: 0.7, bottom: 0.1}, title=\"refsell\", color=red)",
          "name": "Liquidity (poc)",
          "options": {
            "priceScaleId": "right",
            "pivotLength": 2,
            "color": "rgb(129,199,132)",
            "visible": true,
            "src": "close",
            "scaleMargins": {
              "top": 0.08,
              "bottom": 0.26
            },
            "showDown": true,
            "showUp": true,
            "debugDown": false,
            "debugUp": false,
            "drawCount": 2,
            "enableInvalidation": true,
            "enableTarget": true,
            "extendBase": false,
            "levels": "0,1,2,3,5,8,13,21,34,55,89",
            "singleSide": true,
            "targetLevelDown": 66,
            "targetLevelUp": 66,
            "minImpulse": 0,
            "strokeWidth": 0,
            "originWidth": 2,
            "lineColor": "rgb(59,70,101)",
            "originColor": "rgb(41,98,255)",
            "debugColor": "rgba(255,255,255,0.71)",
            "upLineColor": "rgb(255,235,59)",
            "neverSameSide": true,
            "strict": false,
            "extremesOnly": true,
            "delayNeckline": false,
            "minSwings": 2,
            "maxRetracement": -1,
            "twoClosesRule": true,
            "useHeikinAshi": true,
            "useGaps": true,
            "invalidateSwing": true,
            "useTrailStop": false,
            "levelsDown": "0,1, 2, 3, 5, 8, 13, 21, 34, 55,89",
            "levelsUp": "0,1.0, 2, 3, 5, 8, 13, 21, 34, 55,89",
            "fibMult": "0.486548,0.513452",
            "waitForInvalidation": true,
            "compositeOperation": "",
            "leverages": "5,20,50,100",
            "length": 5,
            "opacity": 0.0016,
            "fixedSize": "",
            "threshold": 360,
            "lastValueVisible": false,
            "lineStyle": 0,
            "lineType": 0,
            "lineWidth": 1,
            "priceLineStyle": 1,
            "priceLineVisible": false,
            "minimum": 0,
            "volAvgLength": 5,
            "atrLength": 14,
            "drawAll": true,
            "lengthAtr": 50,
            "lengthMeanVol": 57,
            "merge": true,
            "strokeColor": "rgba(255,235,59,0.5)",
            "sellColor": "rgba(41,251,255,0.01)",
            "buyColor": "rgba(166,41,255,0.01)",
            "showLabel": false,
            "minRange": 0,
            "precision": 36,
            "lengthPivot": 6,
            "density": 0.2,
            "extendInfinite": false,
            "extendLength": -1,
            "showResistances": true,
            "showSupports": true,
            "thickness": 0.2,
            "dualSrc": true,
            "clearGroup": true,
            "step": 25,
            "log": true,
            "useOhlc": false,
            "inverseSource": null,
            "useInverseSource": false,
            "scaleLev": false,
            "scaleFactor": 0.5,
            "logScale": 1000000,
            "minAlpha": 0.3
          },
          "id": "liquidity-poc",
          "priceScaleId": "right",
          "series": [
            "liquidity-poc copy 1",
            "a7ky1hlp",
            "0juguwuu",
            "8xgarqxp",
            "prmmxk77",
            "40td7n5v",
            "mqeo4odt",
            "yuulf2zl",
            "u1b9wmyq",
            "z4dxnnqy",
            "dmxwrh05",
            "sp351vda",
            "66rd4ml1",
            "3veylie5",
            "qaucvlon",
            "ja3ug6n7",
            "0u9rptg3",
            "7noxc7hr",
            "80b6rsos",
            "lb47odwb",
            "fjmes06a",
            "krpffk8p",
            "hmxt2rhi"
          ],
          "displayName": "Liquidity (poc)",
          "unsavedChanges": true
        }
      },
      "priceScales": {
        "right": {
          "scaleMargins": {
            "top": 0.04,
            "bottom": 0.26
          },
          "priceFormat": {
            "precision": 1,
            "minMove": 0.1
          }
        },
        "cvd": {
          "scaleMargins": {
            "top": 0.84,
            "bottom": 0
          }
        },
        "volume_liquidations": {
          "scaleMargins": {
            "top": 0.75,
            "bottom": 0.17
          }
        },
        "volume": {
          "scaleMargins": {
            "top": 0.84,
            "bottom": 0
          }
        },
        "btcmultispot": {
          "scaleMargins": {
            "top": 0.1,
            "bottom": 0.2
          }
        },
        "cvdperp": {
          "scaleMargins": {
            "top": 0.1,
            "bottom": 0.2
          }
        },
        "cvdspot": {
          "scaleMargins": {
            "top": 0.1,
            "bottom": 0.2
          }
        }
      },
      "layouting": false,
      "showIndicators": true,
      "timeframe": "60",
      "refreshRate": 1000,
      "showAlerts": true,
      "showAlertsLabel": true,
      "showLegend": true,
      "fillGapsWithEmpty": true,
      "showHorizontalGridlines": false,
      "horizontalGridlinesColor": "rgba(255,255,255,.1)",
      "showVerticalGridlines": false,
      "verticalGridlinesColor": "rgba(255,255,255,.1)",
      "showWatermark": true,
      "watermarkColor": "rgba(255,255,255,.1)",
      "showBorder": true,
      "borderColor": null,
      "showLeftScale": false,
      "showRightScale": true,
      "showTimeScale": true,
      "hiddenMarkets": {
        "BINANCE_FUTURES:btcusd_perp": false,
        "BITMEX:XBTUSD": false,
        "BYBIT:BTCUSD": false,
        "DERIBIT:BTC-PERPETUAL": false,
        "BINANCE_FUTURES:btcusdt": false,
        "BINANCE_FUTURES:btcbusd": false,
        "BITGET:BTCUSDT_UMCBL": false,
        "BITFINEX:BTCF0:USTF0": false,
        "BITMEX:XBTUSDT": false,
        "BYBIT:BTCUSDT": false,
        "KRAKEN:PI_XBTUSD": false,
        "OKEX:BTC-USD-SWAP": false,
        "OKEX:BTC-USDT-SWAP": false,
        "BITFINEX:BTCUSD": false,
        "COINBASE:BTC-USD": false,
        "BINANCE:btcusdt": false,
        "BINANCE:btcbusd": false,
        "BITGET:BTCUSDT": false,
        "BITFINEX:BTCUST": false,
        "COINBASE:BTC-USDT": false,
        "BITSTAMP:btcusd": false
      },
      "barSpacing": 0.48555231532678533,
      "navigationState": {
        "tab": "script",
        "optionsQuery": "",
        "fontSizePx": 14
      },
      "_id": "chart"
    },
    "settings": {
      "_id": "settings",
      "preferQuoteCurrencySize": true,
      "aggregationLength": 1,
      "calculateSlippage": null,
      "wsProxyUrl": null,
      "disableAnimations": false,
      "autoHideHeaders": true,
      "autoHideNames": true,
      "theme": "light",
      "backgroundColor": "rgb(255,255,255)",
      "textColor": "",
      "buyColor": "rgb(100, 157, 102)",
      "sellColor": "rgb(239, 67, 82)",
      "timezoneOffset": 7200000,
      "useAudio": true,
      "audioVolume": 0.11,
      "audioFilters": {
        "PingPongDelay": true,
        "Compressor": false,
        "Delay": false,
        "HighPassFilter": true,
        "LowPassFilter": false,
        "Chorus": false
      },
      "sections": [
        "settings-trades",
        "timeframe-minutes",
        "timeframe-hours",
        "indicator-right-colors",
        "settings-audio",
        "settings-other",
        "settings-workspaces",
        "trades-thresholds",
        "trades-audio",
        "trades-display",
        "settings-colors",
        "indicator-right-script",
        "indicator-right-default",
        "indicator-right-format"
      ],
      "searchTypes": {
        "recentSearches": true,
        "historical": true,
        "spots": true,
        "perpetuals": true,
        "futures": false,
        "normalize": true,
        "mergeUsdt": true
      },
      "searchQuotes": {},
      "previousSearchSelections": [],
      "searchExchanges": {
        "UNISWAP": false
      },
      "timeframes": [
        {
          "label": "1s",
          "value": "1"
        },
        {
          "label": "3s",
          "value": "3"
        },
        {
          "label": "5s",
          "value": "5"
        },
        {
          "label": "10s",
          "value": "10"
        },
        {
          "label": "15s",
          "value": "15"
        },
        {
          "label": "30s",
          "value": "30"
        },
        {
          "label": "1m",
          "value": "60"
        },
        {
          "label": "3m",
          "value": "180"
        },
        {
          "label": "5m",
          "value": "300"
        },
        {
          "label": "15m",
          "value": "900"
        },
        {
          "label": "21m",
          "value": "1260"
        },
        {
          "label": "30m",
          "value": "1800"
        },
        {
          "label": "1h",
          "value": "3600"
        },
        {
          "label": "2h",
          "value": "7200"
        },
        {
          "label": "4h",
          "value": "14400"
        },
        {
          "label": "6h",
          "value": "21600"
        },
        {
          "label": "8h",
          "value": "28800"
        },
        {
          "label": "12h",
          "value": "43200"
        },
        {
          "label": "1d",
          "value": "86400"
        },
        {
          "label": "21 ticks",
          "value": "21t"
        },
        {
          "label": "50 ticks",
          "value": "50t"
        },
        {
          "label": "89 ticks",
          "value": "89t"
        },
        {
          "label": "100 ticks",
          "value": "100t"
        },
        {
          "label": "200 ticks",
          "value": "200t"
        },
        {
          "label": "610 ticks",
          "value": "610t"
        },
        {
          "label": "1000 ticks",
          "value": "1000t"
        },
        {
          "label": "1597 ticks",
          "value": "1597t"
        }
      ],
      "favoriteTimeframes": {
        "60": "1m",
        "300": "5m",
        "900": "15m",
        "3600": "1h"
      },
      "normalizeWatermarks": true,
      "alerts": false,
      "alertsColor": "rgb(255,0,0)",
      "alertsLineStyle": 2,
      "alertsLineWidth": 2,
      "alertsClick": false,
      "alertSound": null,
      "showThresholdsAsTable": true
    },
    "trades": {
      "liquidations": [
        {
          "id": "liquidation_threshold",
          "amount": 20500,
          "buyColor": "rgba(236,64,122,0.5)",
          "sellColor": "rgba(255,152,0,0.5)",
          "buyAudio": "var srqtR = Math.min(1, gain / 4)\nplay(329.63, srqtR, srqtR*2,0,,,'sine')\nplay(329.63, srqtR, srqtR*4,0.08,,,'sine')",
          "sellAudio": "var srqtR = Math.min(1, gain / 6)\nplay(440, srqtR, srqtR*2,0,,,'sine')\nplay(440, srqtR, srqtR*4,0.08,,,'sine')"
        },
        {
          "id": "liquidation_significant",
          "amount": 41000,
          "buyColor": "rgba(236,64,122,0.6)",
          "sellColor": "rgba(255,152,0,0.7)",
          "buyAudio": "var srqtR = Math.min(1, gain / 4)\nplay(329.63, srqtR, srqtR*4,0,,,'sine')\nplay(329.63, srqtR, srqtR*6,0.08,,,'sine')",
          "sellAudio": "var srqtR = Math.min(1, gain / 6)\nplay(440, srqtR, srqtR*4,0,,,'sine')\nplay(440, srqtR, srqtR*6,0.08,,,'sine')"
        },
        {
          "id": "liquidation_huge",
          "amount": 82000,
          "buyGif": "flying money",
          "sellGif": "flying money",
          "buyColor": "rgba(236,64,122,0.7)",
          "sellColor": "rgba(255,152,0,0.8)",
          "buyAudio": "var srqtR = Math.min(1, gain / 4)\nplay(329.63, srqtR, srqtR*4,0,,,'sine')\nplay(329.63, srqtR, srqtR*8,0.08,,,'sine')",
          "sellAudio": "var srqtR = Math.min(1, gain / 6)\nplay(440, srqtR, srqtR*4,0,,,'sine')\nplay(440, srqtR, srqtR*8,0.08,,,'sine')"
        },
        {
          "id": "liquidation_rare",
          "amount": 410000,
          "buyGif": "explosion",
          "sellGif": "explosion",
          "buyColor": "rgb(156,39,176)",
          "sellColor": "rgb(255,235,59)",
          "buyAudio": "var srqtR = Math.min(1, gain / 10)\nplay(329.63, srqtR, 1,0,,,'sine')\nplay(329.63, srqtR, srqtR*10,0.08,,,'sine')",
          "sellAudio": "var srqtR = Math.min(1, gain / 10)\nplay(440, srqtR, 1,0,,,'sine')\nplay(440, srqtR, srqtR*10,0.08,,,'sine')"
        }
      ],
      "thresholds": [
        {
          "id": "gy81b45x",
          "amount": 36738.4,
          "buyColor": "rgba(119, 148, 92, 0.25)",
          "sellColor": "rgba(239, 67, 82, 0.25)",
          "buyAudio": "play(659.26, gain / 10, 0.1 + gain / 10)",
          "sellAudio": "play(493.88, gain / 10, 0.1 + gain / 10)",
          "buy": "rgba(119, 148, 92, 0.25)"
        },
        {
          "id": "threshold",
          "amount": 150000,
          "buyColor": "rgb(100, 157, 102)",
          "sellColor": "rgb(239, 67, 82)",
          "buyAudio": "play(659.26, 0.05 + gain / 10, 0.1 + ratio * 0.1,0,,0);\nplay(830.6, 0.05 + gain / 10, 0.1 + ratio * 0.1, 0.08,,0)",
          "sellAudio": "play(493.88, 0.05 + gain / 10, 0.1 + ratio * 0.1,0,,0);\nplay(392, 0.05 + gain  / 10, 0.1 + ratio * 0.1, 0.08,,0)",
          "buy": "rgba(60,138,63,0.01)"
        },
        {
          "id": "huge",
          "amount": 500000,
          "buyGif": "cash bullish",
          "sellGif": "cash bearish",
          "buyColor": "rgb(59, 202, 109)",
          "sellColor": "rgb(235, 30, 47)",
          "buyAudio": "play(659.26, 0.05 + gain / 15, 0.1 + ratio * 0.1, 0,,0);\nplay(830.6, 0.05 + gain / 15, 0.1 + ratio * 0.1, 0.08,,0);\nplay(987.76, 0.05 + gain / 15, 0.1 + ratio * 0.1, 0.16,,0);\nplay(1318.52, 0.05 + gain / 15, 0.1 + ratio * 0.1, 0.24,,0)",
          "sellAudio": "play(493.88, 0.05 + gain / 10, 0.2, 0,,0);\nplay(369.99, 0.05 + gain / 10, 0.2, 0.08,,0);\nplay(293.66, 0.05 + gain / 10, 0.2, 0.16,,0);\nplay(246.94, 0.05 + gain / 10, 0.1 + ratio * 0.1, 0.24,,0)"
        },
        {
          "id": "significant",
          "amount": 1469533.8,
          "buyColor": "rgb(0, 255, 127)",
          "sellColor": "rgb(217, 31, 28)",
          "buyAudio": "play(659.26, 0.05 + gain / 25, 0.1 + ratio * 0.13, 0,,0);\nplay(830.6, 0.05 + gain / 25, 0.1 + ratio * 0.13, 0.08,,0);\nplay(987.76, 0.05 + gain / 25, 0.1 + ratio * 0.13, 0.16,,0);\nplay(1318.52, 0.05 + gain / 10, 0.1 + ratio * 0.13, 0.24,,0)",
          "sellAudio": "play(493.88, 0.05 + gain / 25, 0.1 + ratio * 0.13, 0,,0);\nplay(369.99, 0.05 + gain * 1.5 / 10, 0.2, 0.08,,0);\nplay(293.66, 0.05 + gain * 1.5 / 10, 0.2, 0.16,,0);\nplay(246.94, 0.05 + gain * 1.5 / 10, 0.1 + ratio * 0.13, 0.24,,0)"
        },
        {
          "id": "rare",
          "amount": 3660714.7,
          "buyGif": "explosion",
          "sellGif": "explosion",
          "buyColor": "rgb(105,209,108)",
          "sellColor": "rgb(255,0,30)",
          "buyAudio": "play(659.26, 0.05 + gain / 25, 0.1 + ratio * 0.13, 0,,0);\nplay(830.6, 0.05 + gain / 25, 0.1 + ratio * 0.13, 0.08,,0);\nplay(987.76, 0.05 + gain / 25, 0.1 + ratio * 0.13, 0.16,,0);\nplay(1318.52, 0.05 + gain / 10, 0.1 + ratio * 0.13, 0.24,,0)",
          "sellAudio": "play(493.88, 0.05 + gain / 25, 0.1 + ratio * 0.13, 0,,0);\nplay(369.99, 0.05 + gain * 1.5 / 10, 0.2, 0.08,,0);\nplay(293.66, 0.05 + gain * 1.5 / 10, 0.2, 0.16,,0);\nplay(246.94, 0.05 + gain * 1.5 / 10, 0.1 + ratio * 0.13, 0.24,,0)",
          "max": false
        }
      ],
      "audioThreshold": "70000",
      "multipliers": {},
      "maxRows": 100,
      "muted": false,
      "audioPitch": null,
      "audioVolume": 0.01,
      "showPairs": false,
      "showTrades": true,
      "showLiquidations": false,
      "showLogos": true,
      "monochromeLogos": false,
      "showTimeAgo": true,
      "showPrices": true,
      "showHistograms": true,
      "thresholdsMultipler": 0.41,
      "_id": "trades"
    }
  }
}
