---
title: "SLA"
date: 2020-01-02T17:34:33+08:00
draft: false
featuredImg: ""
tags: 
  - SLA
  - MEASURE
  - SDWAN
  - VERSA
---

SLA probe
 
What is the config of SLA probe , make sure recompute timer>sla probe thresh hold value i.e. if your sla probe is 2Sx3 then use recompute timer >6 sec. Also can you enable SLA smoothening and check.
 
" Smoothing involves  taking  a  historical  perspective before  moving  the  traffic  from  the non-compliant data path to the compliant data path. If this check box is disabled, the SLA compliance of a path is checked for every Recompute Interval. However, if this check box is enabled, the system averages the metrics over the smoothing interval instead of the Recompute  Interval.  If  the  path  is  in  the  SLA  compliant  state,  the  metrics  is averaged over the Recompute Interval. The Smoothing Interval must be larger than the Recompute  Interval.  This  is  especially  useful  for  loss-based  SLAs, where  loss measurement  accuracy  depends  on  the  amount  of  packet  samples. For  example,  if  the Recompute Interval is 10 seconds and the Smoothing Interval is 60seconds:-If the path is SLA compliant, the SLA metrics is averaged over the last 10 seconds (last Recompute Interval) to determine SLA compliance.-If  path  is  SLA  non-compliant,  the  metrics  from  the  last 60secondsis  used  to determine SLA compliance. Thus, smoothing helps to react slower to improvements in the network conditions, but guaranteeing its accuracy. The default value for SLA smoothening interval is 120 seconds."
 
Regards,
Ashwani Parashar
ashwani@versa-networks.com
versalogo
 
From: Mohsin Kamal 
Sent: Friday, August 23, 2019 10:40 PM
To: Systems Engineering <versa-syseng@versa-networks.com>
Subject: Recompute timer recommendation
 
Hi All,
 
Do we have any recommended value for recompute timer? Charter has a requirement for sub 3sec convergence for any failures upstream as a result recompute timer has been set to 5 sec and their threshold are 2% packet loss ,200ms latency and 100ms jitter. I am currently seeing lot of SLA violations because of revLoss, however ping comes back clean. My understanding is revLoss represent inline packet loss. I am suspecting that since recompute timer is very small flex-vnf is not able to do inline loss measurement properly. Has anyone else seen this issue?  
 
sdwan      sdwanDatapathSlaNotMet  2019-08-23T16:51:01+0 Charter-ENT: SLA violation for rule Default-Rule on path mrhgmoai-iwb01/ISP-1 to enwdcocd-iwh10/Charter-West for fwdClass fc_be, KPI delay:29 msec fwdLoss:0.00% revLoss:2.90% pduLoss:0.00% fwdDelayVar:0 msec revDelayVar:0 msec cktRxUtil:0% cktTxUtil:0%
 
Thanks,
Mohsin


---

Office365 integration through REST API and first packet app detection

Riverbed keep asking me about our app recognition engine and one of the permanent questions is if we can detect office 365 and other applications from the first packet (before 3-way handshake is complete). Riverbed has been using API integration with Office365 for some time now and they have been using this as a competitive advantage.
Very common use case is to have a default route advertised by the HUB, but use a local break-out for office365 traffic only on all spokes.
 
Right now our position is following:
We use application caching mechanism which allows us to cache destination ip/port and map it to a specific application.
If a customer is creating a PBF rule to forward office365 traffic to a local DIA, the very first flow will go to the HUB, because we can’t recognize application before 3-way handshake has happened for this session and PBF won’t work. But all follow up sessions from any other customer on this FlexVNF to the same destination ip/port will be recognized as office365 from the very first packet even before 3-way handshake is complete, because application is already cached on FlexVNF.
So, technically we can do office365 recognition from the very first packet for second and following flows.
 
Akshay Adhikari gave a little highlights of enhancements we will have with App recognition in 20.2 FlexVNF:
- we speed up the building of the app cache by leveraging dns proxy, so that app cache entries get added for all resolved IP addresses, not just one IP address at a time.
- in cases where we can leverage the http proxy (vfp), (for example, because hosts are configured to access the internet via a proxy-behind-hub and we want to selectively LBO (local breakout), or if we configure a transparent http proxy for port 80/443), it is possible to remove the dependency on the app cache. Of course, this comes at a resource cost - every http connection has to be proxied. 
 
Also, Rahul Vaidya added: starting from 21.1 FlexVNF we will do the same integration as Riverbed and will be able to upload IP/PORT lists of Office365 using SPACK on FlexVNF. We will constantly update list of IPs for O365 and customers will be able to do application recognition from the very first packet of the first flow.
 
Please let me know if you have any questions.

---

The 16.1R2 S9 service release is now available to download from
https://versanetworks.box.com/v/16-1R2-S9-GA
Password: @Versa16.1R2
 
Additionally, the software is also available to download from:
https://upload.versa-networks.com/index.php/s/aZO3IC9fCeB413V
Password: @Versa16.1R2

