---
title:  Frequently Asked Questions
summary: "The most common questions asked by newcomers and users getting started with Superalgos."
sidebar: suite_sidebar
permalink: suite-frequently-asked-questions.html
---

## Before you begin

### Do I need to be a technical person to use Superalgos?

There is extensive documentation and a step by step getting started guide available both as [written instructions](suite-step-0.html) and in [video tutorials](index.html).

That said, Superalgos is in an open beta-stage, still under development. The early-stage pre-release intends to gather feedback from early adopters, who may help shape the software and evolve it into a robust product. We try our best to make installation and operation easy. At this point, the system is directed at tech-savvy individuals with a knack for learning a few PC operator tricks while installing and using the system.

If you don't consider yourself an early adopter and usually go to your 10-year-old for advice on using your PC, you may still give it a shot. Developers and users in the <a href="https://t.me/superalgoscommunity" rel="nofollow" rel="noopener" target="_blank">Community</a> will be happy to give you a hand and help you get up and running.

### Will Superalgos work on my computer?

Superalgos may run in most computers. Please, read the [system requirements](suite-system-requirements) for the details.

### Is Superalgos a web-based service?

No. What you will get is a client application that runs entirely on users' machines. This is to fulfill the design principle of a trustless deployment: you don't need to trust any third party with your strategies, exchange API keys, personal information, or funds.

There is a thorough description of system features and functionality <a href="https://superalgos.org/" target="_blank">on the website</a>.

### Why is such an amazing piece of software open-source?

Because the Superalgos Project is about building a Collective Trading Intelligence, and the Superalgos software is the backbone of the technology that enables creating such intelligence, while collaborating. Please find the full explanation in this <a href="https://medium.com/superalgos/why-we-open-sourced-superalgos-55a5cbf83922?source=friends_link&sk=68755ad373cc64c3a90318405f6c9a65" rel="nofollow" rel="noopener" target="_blank">Medium post</a>. You may also find more information about the project's long-term vision <a href="https://superalgos.org/about-project.shtml" target="_blank">on the web site</a>.

### Is it safe to use Superalgos? Will I be spied, robbed of personal information, or scammed?

Using Superalgos is as safe as it gets. This is why:

1. The software is open-source. This means that any developer or technical person out there may read and audit the code and certify there is no hidden malware or anything of the sort. 

1. Moreover, the system runs on the uncompiled code, that is, all of the code may be easily read by any programmer. There are no binary files which are much harder to interpret and audit.

1. The code is maintained on GitHub using <a href="https://en.wikipedia.org/wiki/Git" rel="nofollow" rel="noopener" target="_blank">GIT technology</a> by which every single change made over the years is recorded and may be audited at any point.

1. The software is free and open-source because it is the backbone of the project. The project will succeed if the software gets adopted. Thus, the interest of the project is perfectly aligned with the interest of users. The better the software, the more people will use it, and the larger the Collective Trading Intelligence the project may achieve.

1. The software runs in your computer, and connects directly to the exchange, using your API key to access your account, trading directly from within your account. No third party is involved in any of your transactions. You do not need to trust your API keys, your funds, your personal information, or your strategies with anyone.

1. Community-built strategies are open-source too. You may backtest them, verify their performance, set your parameters, and even modify them and produce your versions if you wish. They too are maintained on GitHub using GIT technology.

1. We do not make any irresponsible claims regarding the performance of strategies. We simply report our backtesting results which you may verify, and we report the live performance since the day they where released. You may verify that information yourself as well. 

1. Strategies are easy to read too and are stored in a file in the ```JSON``` format. All of the rules are written using simple mathematical statements. You may easily change the rules and test how the changes affect the results. 


## Live trading

### What exchanges may I work with?

The system implements the <a href="https://github.com/ccxt/ccxt/" rel="nofollow" rel="noopener" target="_blank">CCXT library</a>, which allows connecting to a <a href="https://github.com/ccxt/ccxt/wiki/Exchange-Markets" rel="nofollow" rel="noopener" target="_blank">vast list of exchanges</a>. However, many exchanges do not fully comply with the standards established by the library.

For a list of tested exchanges, please refer to the <a href="https://github.com/Superalgos/Superalgos/blob/master/README.md#exchange-testing-queue" rel="nofollow" rel="noopener" target="_blank">Exchange Testing Queue</a> reference list. 

You are free to try exchanges that haven't been tested by the team. We'd be happy to hear about your tests. That said, it is highly recommended to start with tried and tested exchanges until you become proficient with using the system before venturing into the unknown territory of untested exchanges.

### Do I need to have an account with an exchange to use Superalgos?

You will need an account with a <a href="https://github.com/Superalgos/Superalgos/blob/master/README.md#exchange-testing-queue" rel="nofollow" rel="noopener" target="_blank">supported exchange</a> and an exchange API key if you decide to trade live. You may use Superalgos to get started, to download data from exchanges, to build and to test trading strategies without an exchange account.

### Do I need to trust my API keys to someone?

No. The software runs in your machine, and you set your API keys in your machine only. The system running in your machine connects with the exchange only; no third parties intervene in any way in your transactions with the exchange.

### Is trading fully automated?

Yes. It may be if you choose to run a live <a data-toggle="tooltip" data-original-title="{{site.data.network.session}}">trading session</a>.

### Do I need to have my machine and the system running to trade live?

Yes. The backend application must be running a live <a data-toggle="tooltip" data-original-title="{{site.data.network.session}}">trading session</a> to place orders at the exchange. If you turn your computer off or stop Superalgos, the system will not trade live during that time. 

You may close the fronted application running on the browser at any time. Only the backend application running on the console needs to be running at all times when trading live.

### What happens if Superalgos or the machine shuts down unexpectedly?

In case the system is stopped or stops unexpectedly after a position has been taken, the system does not resume the transaction once it comes back online. In such a case, the position must be managed and closed manually.



## Strategies

### May I create my own strategies? Do I need to write computer code?

Yes and no! Building, testing, and deploying strategies is the core competency of Superalgos. You don't need to write computer code... only simple statements with a specific [syntax](suite-syntax-overview.html) to create conditions and formulas, following a framework that guides you in the process of setting up a [trading system](suite-trading-systems.html).

However, if you can code you may have an edge building more complex logic in JavaScript.

### May I get a ready-to-use strategy and use it to trade live?

Yes. The strategies available to use in Superalgos are the ones you may create yourself and those open-sourced by the Community. If you intend to use a strategy you didn't create yourself, it is highly recommended that you study the strategy, test it, and understand how it works before committing to trade live with it.

Superalgos ships with a few example strategies and the getting started guide teaches you how to run them in Superalgos.

{% include live-trading-warning.html %}

### How does the strategy shipping with Superalgos work? Is it profitable?

Please check the <a href="https://github.com/Superalgos/Strategy-BTC-WeakHandsBuster" rel="nofollow" rel="noopener" target="_blank">Weak-hands Buster README file</a> for the details. The documentation discusses the strategy's performance in live trading and backtesting contexts.

{% include live-trading-warning.html %}

### May I configure the open-source strategy to my liking?

Definitely. You should!

A live trading session has a few [parameters](suite-parameters.html) that you must configure before running it.

And you may also review, test, and modify the rules within the trading system.

{% include live-trading-warning.html %}

### How risky is it to trade with open-source strategies?

Trading crypto-assets is an inherently risky activity. You may lose all of your capital. We can not asses the risks of trading for you. Please, study the strategies you wish to use, do your own research, and consult your financial advisor.

{% include live-trading-warning.html %}



## Support

### What if I need help? Do you have customer support?

Superalgos is on open Community of people pursuing a common goal. The Community is thrilled to have more people joining the cause and is happy to answer questions and help new users get started with Superalgos. It is kindly suggested to read these FAQs, the troubleshooting section in the documentation, and to closely follow the instructions on the getting started guide. That said, please feel free to ask questions in the <a href="https://t.me/superalgoscommunity" rel="nofollow" rel="noopener" target="_blank">Community Telegram</a>.

Superalgos is not commercial software, therefore, there is no such thing as a customer or customer support for that matter.

### May I ask for features I may be missing?

Yes. We keep a wish list for new features in the form of <a href="https://github.com/Superalgos/Platform/issues" rel="nofollow" rel="noopener" target="_blank">issues in the Superalgos repository</a>. If you are missing a key feature, feel free to open an issue starting the subject with the word ```Improvement:```. Please be thorough on your explanation about what you wish and how you envision the feature should work, and make sure you follow the thread so that you may answer questions the developers may have.

We make no promises as of what features may be developed when, but we do our best to keep up with the Community's requests.
