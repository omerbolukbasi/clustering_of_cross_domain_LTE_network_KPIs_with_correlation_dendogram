# Clustering of Cross Domain LTE Network KPI's With Correlation Dendogram

An implementation of **Dendogram Clustering** for grouping related KPI's into same groups. This implementation provides the trend similarities over cross domain KPI's which can be used in performance degredation troubleshooting.

In this implementation there are 4 different KPI domains: GGSN, MME, TAS, UAG

Within these domains all KPI's are collected in a pool and correlation matrix is calculated with using **Pearson** method. With using this correlation matrix a **Dendogram** is composed and presented in the code.

![image](https://user-images.githubusercontent.com/44832162/148109017-6ab1cf87-d628-4746-978c-171073cc7c57.png)

In the Dendogram, different colors of KPI's represent different domains as shown in the title. And the colors of horizontal lines represent different correlation groups. The sensitivity threshold of correlation groups can be adjusted in the code. 

With this diagram, KPIs from cross domains that have similar past trends can be extracted from the groups. This information is beneficial for understanding the root cause of any anomaly occured in this group. For instance if 2 domains are exist in a group that has a past anomally, troubleshooter must focus on the specific changes done in these two domains only. Any change done in one domain might also effect the other domain. 

For instance in the first group (first three green horizontal lines), even the SGSN's and TAS KPI's are from different domains, their past trends are similar. And the anomalies occured in the last parts are also identical which means same influencer is effect as a root cause to these two domains. Trends are as follows.

![image](https://user-images.githubusercontent.com/44832162/148110301-2f57c0db-992c-4e8f-9402-6608bc853534.png)
