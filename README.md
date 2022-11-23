# Econ 101: National Accounts modelling with graphnets

- NFC: Non-financial corporations
- FC: Financial corporations
- GG: General government
- HH + NPISH: Households + NPISH
- RW: Rest of the world


Publicly available quarterly macroeconomic data for multiple countries:
- Nodes: assets and liabilities by sector and instrument
- Edges: transactions
- Edge features: policy variables (e.g. tax rates, interest rates, etc.), ‘environment’ variables (e.g. GDP growth, inflation, country ID, etc.), impact

Proposal: use GNN to learn the impact of economic policies in order to predict (simulate) the effects of planned policy changes

Datasets sources:
- ECB website: https://sdw.ecb.europa.eu/browse.do?node=9691132
- European Central Bank datasets from huggingface: https://huggingface.co/datasets/ecb
- ECB interest rates: https://www.kaggle.com/datasets/addasdaw/european-central-bank-interest-rates-19992021

[![Stand With Ukraine](https://raw.githubusercontent.com/vshymanskyy/StandWithUkraine/main/banner2-direct.svg)](https://stand-with-ukraine.pp.ua)
