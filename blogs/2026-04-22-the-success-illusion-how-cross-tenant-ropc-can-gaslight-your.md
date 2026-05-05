---
title: "The \"Success\" Illusion: How Cross-Tenant ROPC Can Gaslight Your SOC and Poison Data"
url: "https://www.varonis.com/blog/how-cross-tenant-ropc-can-gaslight-your-soc-and-poison-data"
date: "Wed, 22 Apr 2026 04:00:00 GMT"
author: "Ben Zion Lavi"
feed_url: "https://www.varonis.com/blog/rss.xml"
---
<p>Cybersecurity&nbsp;professionals&nbsp;live by a simple axiom:&nbsp;<strong>Logs&nbsp;don't&nbsp;lie.</strong>&nbsp;&nbsp;</p>  
<p>We build entire ecosystems around this truth&nbsp;—&nbsp;our SIEMs,&nbsp;UEBA models, and&nbsp;automated response playbooks, etc.,&nbsp;all rely on the binary distinction between a "failed" login and a "successful" one.&nbsp;</p> 
<p>So, what happens when an attacker can generate a sign-in that appears legitimate in&nbsp;your Entra ID (Azure AD) environment, creating a successful authentication event that may look like it bypasses MFA and conditional access policies, without gaining access to your data?&nbsp;</p> 
<p><a href="https://www.varonis.com/varonis-threat-labs?hsLang=en">Varonis Threat Labs </a>explored a nuance in the Resource Owner Password Credentials (ROPC) protocol that allows the exact scenario above. While the immediate threat isn't necessarily data&nbsp;exfiltration, the implications for your security operations, budget, and data integrity are far more disturbing.&nbsp;Continue reading to learn more.&nbsp;</p> 
<h2>The&nbsp;mechanism: A&nbsp;log&nbsp;without a&nbsp;login&nbsp;</h2> 
<p>Authenticating activities without logging&nbsp;relies&nbsp;on a "cross-tenant" architecture. When an attacker has a valid username and password for your organization (Tenant A), they typically&nbsp;can't&nbsp;log in because&nbsp;of&nbsp;enforced&nbsp;MFA or block legacy protocols.&nbsp;</p> 
<p>However, if the attacker authenticates these credentials against a&nbsp;<em>different</em>, permissive tenant (Tenant B), a fascinating desync occurs:&nbsp;</p> 
<ol> 
 <li><strong>Your&nbsp;tenant (home)</strong>&nbsp;verifies the password and logs the event&nbsp;</li> 
 <li><strong>The&nbsp;other&nbsp;tenant (resource)</strong>&nbsp;checks the Conditional Access policies&nbsp;</li> 
</ol> 
<p>Since the&nbsp;<em>other</em>&nbsp;tenant has no policies against this user, the authentication flows through. The result? Your SIEM lights up with a&nbsp;"Sign-in: Success"&nbsp;event. On the surface level, and to many monitoring tools, it appears like a user successfully bypassed your expected authentication controls.&nbsp;</p> 
<h2>The&nbsp;real&nbsp;danger:&nbsp;poisoning the&nbsp;well&nbsp;</h2> 
<p>Even if the attacker&nbsp;doesn't&nbsp;gain&nbsp;access to your files&nbsp;due to being&nbsp;in a different&nbsp;tenant,&nbsp;security teams should still care because confusion is a powerful weapon in today’s modern cyber landscape.&nbsp;&nbsp;</p> 
<p>Let’s&nbsp;dive into how&nbsp;this can&nbsp;transpire&nbsp;in your environment:&nbsp;</p> 
<h3><strong>1. Poisoning UEBA and ML models</strong></h3> 
<p>Modern security relies on Machine&nbsp;Learning&nbsp;(ML)&nbsp;to&nbsp;establish&nbsp;a "baseline" of normal behavior. By flooding your logs with "fake" successful logins from random geolocations or IPs, an attacker effectively "poisons the well"&nbsp;With false information, such as:&nbsp;</p> 
<ul> 
 <li>A&nbsp;user "successfully logs in" from 50 different countries in an hour,&nbsp;skewing&nbsp;the model’s threshold for "impossible travel"&nbsp;</li> 
 <li>The system begins to treat anomalies as noise, potentially masking the&nbsp;<em>real</em>&nbsp;attack happening in the shadows&nbsp;</li> 
 <li>Security controls may act based on the false positive alerts generated based on these logs, which may disrupt production systems&nbsp;</li> 
</ul> 
<h3><strong>2. The financial and&nbsp;operational&nbsp;toll (SOC Tax)</strong>&nbsp;</h3> 
<p>Every&nbsp;false&nbsp;positive has a price tag. Imagine your SOC analyst sees a&nbsp;successful&nbsp;login from a known malicious IP in Russia. They&nbsp;treat it as a&nbsp;critical&nbsp;incident:&nbsp;</p> 
<ul> 
 <li>They wake up the CISO&nbsp;</li> 
 <li>They disable the&nbsp;user&nbsp;account&nbsp;</li> 
 <li>They spend hours investigating a breach that&nbsp;technically never&nbsp;happened&nbsp;</li> 
</ul> 
<p>An attacker can script this process, generating thousands of these "ghost logins." This&nbsp;isn't&nbsp;just annoying;&nbsp;it's&nbsp;a&nbsp;Denial-of-Service (DoS) attack on your human analysts. It forces you to burn budget and&nbsp;manpower&nbsp;chasing ghosts.&nbsp;</p> 
<h3><strong>Compliance and&nbsp;audit&nbsp;nightmares</strong>&nbsp;</h3> 
<p>How&nbsp;would&nbsp;you explain to an auditor that your logs show 500 successful logins without MFA, even&nbsp;though MFA&nbsp;should be&nbsp;enforced everywhere?&nbsp;The "log&nbsp;integrity" is compromised. You are no longer looking at a record of truth, but a record of partial&nbsp;truths.&nbsp;</p> 
<h2><strong>Disclosure</strong></h2> 
<p><span style="font-weight: normal;">Varonis reported this behavior to Microsoft through the appropriate disclosure channels. Microsoft assessed the issue as low severity because, while the technique can create misleading successful sign-in events, it does not grant access to cloud resources or tenant data. </span></p> 
<p><span style="font-weight: normal;">From a SOC and audit perspective, the concern remains significant: defenders may still interpret these events as evidence of meaningful access, triggering investigations, alerts, and incident-response workflows based on telemetry that does not necessarily reflect resource compromise.</span><strong>&nbsp;</strong></p> 
<h2><strong>The takeaway: Context is king</strong>&nbsp;</h2> 
<p>This vulnerability&nbsp;highlights a critical gap in cloud security:&nbsp;<strong>Static logs are no longer enough.</strong> Many vendors tend to classify ROPC as "low severity" when data wasn't accessed. However, for a CISO managing&nbsp;a SOC, the severity is high.&nbsp;</p> 
<p>To properly defend against this, we need to stop looking at "login&nbsp;status" in a vacuum.&nbsp;Organizations&nbsp;need&nbsp;to implement a&nbsp;data-centric&nbsp;security&nbsp;strategy.&nbsp;&nbsp;</p> 
<p>Flip the question from,&nbsp;<em>"Did they log in?"</em>&nbsp;to&nbsp;<em>"Did they access data?&nbsp;Did they&nbsp;access&nbsp;a resource&nbsp;</em><em>inside&nbsp;our tenant?"</em>&nbsp;</p> 
<p>If your security tool only looks at the front door, it can be fooled by someone ringing the doorbell. You need visibility into what happens&nbsp;<em>inside</em>&nbsp;the house.&nbsp;&nbsp;</p> 
<p>Next time&nbsp;you’re&nbsp;writing a SIEM rule, sprinkle a little salt on those auth logs —&nbsp;they’re&nbsp;not always as honest as they look. Explore more from <a href="https://www.varonis.com/blog/tag/threat-research#blog-listing">Varonis Threat Labs</a>.&nbsp;</p>  
<img alt="" height="1" src="https://track.hubspot.com/__ptq.gif?a=142972&amp;k=14&amp;r=https%3A%2F%2Fwww.varonis.com%2Fblog%2Fhow-cross-tenant-ropc-can-gaslight-your-soc-and-poison-data&amp;bu=https%253A%252F%252Fwww.varonis.com%252Fblog&amp;bvt=rss" style="width: 1px!important;" width="1" />
