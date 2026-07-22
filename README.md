# Dublin Bay — TRMNL plugin data

Live sea conditions for Dublin Bay as a [TRMNL](https://usetrmnl.com) e-ink
plugin: sea temperature (with weekly trend and record/anomaly context from a
2014-onwards archive), wave height, wind, Dublin Port tides, EPA bathing-water
quality, and active swim alerts.

[`trmnl.json`](trmnl.json) is refreshed roughly hourly by the
[@DublinBayTemp](https://twitter.com/DublinBayTemp) bot, which corroborates
readings across sources before publishing. TRMNL polls this static file, so
plugin installs add no load to the underlying APIs.

## Use it on your TRMNL

Create a private plugin with strategy **Polling** and this URL:

```
https://raw.githubusercontent.com/abcdggs/dublin-bay-trmnl/main/trmnl.json
```

then paste the templates from [`templates/`](templates/) into the markup
editor (full / half horizontal / half vertical / quadrant). A ~1 hour refresh
rate matches how often the data changes.

## Data sources

- Sea temp, waves, wind: [Dublin Bay Buoy](https://dublinbaybuoy.com) (fallback: Irish Lights ERDDAP)
- Tides: [Marine Institute ERDDAP](https://erddap.marine.ie), Dublin_Port station
- Water quality & swim alerts: [EPA Bathing Water API](https://data.epa.ie)
