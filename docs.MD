I think, it would be best to do some prototyping to discover what is possible to achieve here.Probably, it would make sense to begin with less granular sector data, i.e. use aggregates, such as "Financial corporations" without splitting them into banks, funds, etc. So the main sectors would be:

- S11: Non-financial corporations
- S12: Financial corporations
- S13: General government
- S14: Households
- S15: Non-profit institutions serving households

Some data is only available for certaing groups of sectors, e.g. S14 + S15.For every sector there are data on Stocks (nodes) and Flows (edges).Stocks are the closing balance sheets. These can be split into various instruments (e.g. loans, shares, etc.) and counterparties (I suggest sticking to the same sectors for now). Some examples of stocks:

 - This table contains the amounts of LISTED SHARES issued by non-financial corporations (S12) and HELD by households and non-profits serving households (S14+S15) inside each country at the end of the quarter: https://sdw.ecb.europa.eu/browseTable.do?org.apache.struts.taglib.html.TOKEN=44915f57[…]=332.QSA.Q.N.SK.W2.S1M.S11.N.A.LE.F511._Z._Z.XDC._T.S.V.N._T
 - This table contains the amounts of LOANS taken by non-financial corporations (S12) and PROVIDED by households and non-profits serving households (S14+S15) inside each country at the end of the quarter: https://sdw.ecb.europa.eu/browseTable.do?org.apache.struts.taglib.html.TOKEN=b08eb16b[…]KEY=332.QSA.Q.N.SK.W2.S1M.S11.N.A.LE.F4.T._Z.XDC._T.S.V.N._T 
 - This table contains the amounts of BONDS issued by non-financial corporations (S12) and HELD by households and non-profits serving households (S14+S15) inside each country at the end of the quarter: https://sdw.ecb.europa.eu/browseTable.do?org.apache.struts.taglib.html.TOKEN=4e4b4549[…]KEY=332.QSA.Q.N.SK.W2.S1M.S11.N.A.LE.F3.T._Z.XDC._T.S.V.N._T

The stocks are measured at the end of every calendar quarter. Changes between those moments are the result of transactions (Flows). Some examples of flows:

This table contains the amounts of LOANS taken by non-financial corporations (S12) and INCREASED/DECREASED by households and non-profits serving households (S14+S15) inside each country during the quarter: https://sdw.ecb.europa.eu/browseTable.do?org.apache.struts.taglib.html.TOKEN=2e368df4[…]_KEY=332.QSA.Q.N.SK.W2.S1M.S11.N.A.F.F4.T._Z.XDC._T.S.V.N._T

This table contains the amounts of BONDS issued by non-financial corporations (S12) and BOUGHT/SOLD by households and non-profits serving households (S14+S15) inside each country during the quarter: https://sdw.ecb.europa.eu/browseTable.do?org.apache.struts.taglib.html.TOKEN=444dc78d[…]_KEY=332.QSA.Q.N.SK.W2.S1M.S11.N.A.F.F3.T._Z.XDC._T.S.V.N._T

So the initial idea, I guess, would be to collect the data into a structure readable by a graphnet and then see how to add some context features, such as interest rates or tax rates and see if the graphnet can learn how nodes "move" given certain context features
