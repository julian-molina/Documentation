<!--------------------------------------------- TITLE AND DEFINITION starts -->

{% assign title = "List of Tested Exchanges" %}

<!--------------------------------------------- TITLE AND DEFINITION ends -->

{% if include.content == "more" %}
<details class='detailsCollapsible'><summary class='nobr'>Click to learn about the {{ title | downcase }}{{plural}}
</summary>
{% endif %}

{% if include.content != "no" %}

<!--------------------------------------------- CONTENT starts -->

The system implements the <a href="https://github.com/ccxt/ccxt/" rel="nofollow" rel="noopener" target="_blank">CCXT library</a> which allows connecting to a <a href="https://github.com/ccxt/ccxt/wiki/Exchange-Markets" rel="nofollow" rel="noopener" target="_blank">vast list of exchanges</a>. However, many exchanges do not fully comply with the standards established by the library.

The following is the current state of tests on different exchanges:

| Exchange | OHLCVs Capability&nbsp;[*] | Market History | Trading Capability&nbsp;[**] | Comments |
| :--- | :---: | :---:|  :---: | :--- | 
| Binance | &#x2611; | Starting Sep, 2017  | &#x2611;| <strong>Fully tested. Starting with Binance is recommended as the experience is seamless.</strong> |
| Bitfinex | &#x2611; | 1 year | &#x2611; | Tested, with issues: we have experienced the <a href="https://docs.bitfinex.com/docs/requirements-and-limitations#rest-rate-limits" rel="nofollow" rel="noopener" target="_blank">ERR_RATE_LIMIT</a> error despite the fact that Superalgos sends a maximum of two requests per market / bot /  minute when trading live. |
| Bitmex | &#x2611; | | &#x2612; | The concept of a *contract* is not yet implemented within Superalgos, thus, trading is not enabled yet. |
| Kraken | &#x2612;  | Historical data may only be accessed by id, not by date, thus not available at the moment. | &#x2610; | |
| Poloniex | &#x2612; | Only 5-minutes time frame available in OHLCV data, while 1-minute is required, thus not available at the moment. | &#x2610; |  |
| Bittrex | &#x2611; | A few weeks, depending on the market. | &#x2612; | Live trading not available because Bittrex allows limit orders only (Superalgos may only place market orders at the moment). |
| Gemini | &#x2611; | A few hours. | &#x2610; | |
| HitBTC | &#x2610; | | &#x2610; | |

[*] The ability to fetch historic data for backtesting purposes has been verified.

[**] The ability to run strategies in live-trading mode has been verified.

You are free to [test exchanges](suite-how-to-test-new-exchanges.html) that haven't been tested by the team. That said, it is highly recommended to start with tried and tested exchanges until you become proficient with using the system before venturing into the unknown landscape of untested exchanges.

<!--------------------------------------------- CONTENT ends -->

{% endif %}

{% if include.extended == "more" and include.content != "more" %}
<details class='detailsCollapsible'><summary class='nobr'>Click to learn how to {{ title | downcase }}{{plural}}
</summary>
{% endif %}

{% if include.extended != "no" %}

<!--------------------------------------------- EXTENDED starts -->

XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX

<!--------------------------------------------- EXTENDED ends -->

{% endif %}

{% if include.more == "yes" %}
</details>
{% endif %}