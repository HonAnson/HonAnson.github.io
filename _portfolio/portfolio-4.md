---
title: "Integrating Zero Cost Proxy in MASE"
excerpt: "Using ensumble of zero cost proxy - a meta proxy, for better predict neural network architecture performance<br/><img src='/images/portfolio_cover/proxy.png'>"
collection: portfolio
---

### --- Code available [here](https://github.com/HonAnson/mase) --- 

In this project, I worked with my partner as a pair and added functionality in the research tool Machine-Learning Accelerator System Exploration (MASE). MASE is a tool for exploring methodologies that accelerate large ML models, including adding functionalities such as quantization and neural architecture search (NAS).

In our project, we added a `proxy` action and `proxy_strategy`, whcih allow integration of zero-cost proxies with existing bayesian based search algorithms. Zero-cost proxy refers to metrics for a given neural network architecture and a data sets the model will be trained and inference from, and predicts the performance of the network on that datasets without extensively training the network. More about zero-cost proxies [here](https://arxiv.org/abs/2210.03230)


**Proxy**
* Added `proxy` action in MASE command line interface, major changes in path `machop/chop/actions/proxy/...`
* Integrated `NasBench201` and `NasBench301` search space into MASE proxy action
* Integrated 13 zero cost proxies, including `fisher`, `jacov`, `params`, etc... from ℕ𝔸𝕊-𝔹𝕖𝕟𝕔𝕙-𝕊𝕦𝕚𝕥𝕖-ℤ𝕖r𝕠 into MASE proxy action
* Included sample configuration for `proxy` action in path `machop/configs/nas/proxy_nas.toml`
* Included demo for training a meta-proxy from `NasBench201` search space on CIFAR10 datasets


**Search with proxy**
* Added `proxy` search strategy in MASE `search` action on `Val Accuracy` metric, major changes in path `machop/chop/actions/search/strategies/strats_proxy.py`
* Integrated 13 zero cost proxies, including `fisher`, `jacov`, `params`, etc... from ℕ𝔸𝕊-𝔹𝕖𝕟𝕔𝕙-𝕊𝕦𝕚𝕥𝕖-ℤ𝕖r𝕠 into MASE search action, `proxy_strategy` search strategy
* Included sample configuration for proxy search strategy in path `machop/configs/nas/search_nas.toml`

**Others**
* Fixed bug on invalid search iteration
* Included proxy scores for 8901 architecture sampled from `NasBenchNLP`






