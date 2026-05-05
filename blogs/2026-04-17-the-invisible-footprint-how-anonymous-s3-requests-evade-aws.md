---
title: "The Invisible Footprint: How Anonymous S3 Requests Evade AWS Logging"
url: "https://www.varonis.com/blog/anonymous-s3-requests-evade-aws-logging"
date: "Fri, 17 Apr 2026 13:00:02 GMT"
author: "Maya Parizer"
feed_url: "https://www.varonis.com/blog/rss.xml"
---
<p>Varonis Threat Labs (VTL) discovered an evasive vulnerability that limits visibility into anonymous requests in CloudTrail Network Activity events. Regardless of whether the bucket's permissions allow or deny anonymous access, there were no logs in the Network Activity trail indicating any anonymous requests.&nbsp;In some cases, there were no logs at all.&nbsp;</p>  
<p>Without anonymous activity being logged, organizations risk attackers inside their private cloud networks interacting with public buckets invisibly, evading detection by security teams entirely.</p> 
<p>This discovery&nbsp;follows&nbsp;our publication, <a href="https://www.varonis.com/blog/exploiting-vpc-endpoints-for-s3buckets?hsLang=en">The Silent Attackers: Exploiting VPC Endpoints to Expose AWS Accounts Without a Trace</a>, which revealed how VPC endpoint policies could have been abused to expose the AWS account IDs of any valid S3 bucket, a vulnerability AWS quickly fixed. We are thankful for the collaboration between&nbsp;VTL&nbsp;and AWS Vulnerability Disclosure Program to ensure systems are safe.&nbsp;&nbsp;</p> 
<p>Continue reading to learn how anonymous S3 requests can evade AWS logging.&nbsp;&nbsp;</p> 
<h2><strong>W</strong><strong>hat is&nbsp;</strong><strong>anonymous</strong><strong>&nbsp;access&nbsp;</strong><strong>in</strong><strong>&nbsp;S3 buckets?</strong>&nbsp;</h2> 
<p>Anonymous&nbsp;access&nbsp;refers&nbsp;to&nbsp;interactions&nbsp;with <a href="https://www.varonis.com/blog/create-s3-bucket?hsLang=en">AWS&nbsp;S3&nbsp;buckets</a>&nbsp;where the requester&nbsp;is not required&nbsp;to&nbsp;provide&nbsp;authentication&nbsp;credentials.&nbsp;Anonymous requests are typically used to access publicly available S3 resources and do not include a signature or any identifying information about the requester.&nbsp;</p> 
<h2>How&nbsp;the attack&nbsp;works&nbsp;</h2> 
<p>Anonymous requests did not appear in networking trails&nbsp;while conducting our research.&nbsp;&nbsp;</p> 
<p>In Amazon CloudTrail,&nbsp;the&nbsp;primary distinction&nbsp;between data events and management events&nbsp;is that&nbsp;management events&nbsp;are always collected and&nbsp;can be found in the event history or a&nbsp;configured&nbsp;trail,&nbsp;whereas&nbsp;a trail&nbsp;must&nbsp;be configured to collect&nbsp;data events.&nbsp;Events by anonymous actors that are logged in data or management events did not have a corresponding Network Activity event.&nbsp;</p> 
<p>Let’s&nbsp;break&nbsp;down&nbsp;anonymous requests&nbsp;into cases&nbsp;based on the&nbsp;VPC endpoint policy and the&nbsp;target bucket:&nbsp;</p> 
<ul> 
 <li>When an attacker uses anonymous access&nbsp;within a VPC&nbsp;to get data from a bucket&nbsp;within&nbsp;the account, requests&nbsp;made by an anonymous actor trigger a log&nbsp;in the account.&nbsp;</li> 
 <li>When an&nbsp;attacker uses anonymous access&nbsp;within a VPC&nbsp;to get data from a bucket&nbsp;external to&nbsp;the account,&nbsp;no events&nbsp;were&nbsp;logged&nbsp;in the account at all.&nbsp;</li> 
</ul> 
<p>But,&nbsp;what about the target account?&nbsp;&nbsp;</p> 
<p>When an anonymous request was made to an external S3 bucket through a VPC endpoint,&nbsp;no CloudTrail event was generated at&nbsp;the&nbsp;source account&nbsp;—&nbsp;neither Network Activity, nor management/data events.&nbsp;&nbsp;</p> 
<p>Do we have logs at the target account?&nbsp;</p> 
<ul> 
 <li>If the VPC endpoint policy&nbsp;allowed&nbsp;access, anonymous requests generated&nbsp;management/data events in the target account.&nbsp;</li> 
</ul> 
<ul> 
 <li>If the VPC endpoint policy&nbsp;denied&nbsp;access, the request&nbsp;was&nbsp;blocked at the network layer. In this case, no events&nbsp;were&nbsp;created, including in&nbsp;Network Activity, management/data trails, and in both accounts.&nbsp;</li> 
</ul> 
<p>By denying the endpoint policy in the compromised account, attackers could have interacted with public buckets anonymously and invisibly, evading detection&nbsp;by security teams&nbsp;entirely.&nbsp;</p> 
<p>The&nbsp;diagram below shows how anonymous requests&nbsp;were&nbsp;processed&nbsp;before the fix&nbsp;and what events&nbsp;were&nbsp;shown for anonymous requests to&nbsp;all internal and external buckets.&nbsp;</p> 
<h2><strong>How&nbsp;missing logs&nbsp;impact&nbsp;enterprises and security teams</strong>&nbsp;</h2> 
<p>When logs are missing, the consequences are severe.&nbsp;&nbsp;</p> 
<p>Imagine an attacker compromising&nbsp;an internal application server in your private VPC. From there, they&nbsp;can&nbsp;use the existing VPC endpoint to connect to an external S3 bucket they control. Because the traffic flows through the VPC endpoint, no events are logged in your&nbsp;source&nbsp;AWS account when using anonymous access. The attacker can&nbsp;then&nbsp;quietly upload sensitive&nbsp;business&nbsp;data or intellectual property to their bucket without triggering alerts. When&nbsp;your security team&nbsp;investigates&nbsp;later&nbsp;on, there&nbsp;is&nbsp;no forensic trail&nbsp;—&nbsp;no evidence of what&nbsp;data&nbsp;was taken, when&nbsp;it was&nbsp;stolen, or&nbsp;information on who took it. This&nbsp;lack of visibility&nbsp;makes detection and response&nbsp;nearly impossible&nbsp;for enterprises.&nbsp;</p> 
<p>One&nbsp;might assume that the absence of anonymous events is harmless, but&nbsp;that’s&nbsp;misleading.&nbsp;Despite them&nbsp;providing&nbsp;only minimal context&nbsp;of&nbsp;the identity&nbsp;making the request&nbsp;anonymous&nbsp;events serve&nbsp;as&nbsp;an&nbsp;indication&nbsp;that&nbsp;activity&nbsp;is happening&nbsp;in your environment&nbsp;and&nbsp;gives security teams a chance to investigate and enforce controls before data loss occurs.&nbsp;</p> 
<p>Without&nbsp;logs, there&nbsp;is&nbsp;absolutely&nbsp;zero visibility, leaving organizations&nbsp;unaware&nbsp;of&nbsp;the activity and unable to detect or respond until the damage is already done.&nbsp;Other examples&nbsp;include:&nbsp;</p> 
<ul> 
 <li>An attacker downloading&nbsp;malware from their S3&nbsp;bucket into a VPC behind a VPC endpoint&nbsp;</li> 
 <li>Attacking&nbsp;other companies from the victim organization’s cloud network&nbsp;&nbsp;</li> 
</ul> 
<h2><strong>AWS’&nbsp;response</strong>&nbsp;</h2> 
<p>In partnership with AWS, updates were made to log all anonymous API requests made to external S3 buckets. Here is what AWS had to say:&nbsp;</p> 
<p><em>“AWS released updates that change AWS CloudTrail's logging behavior for Virtual Private Cloud (VPC) endpoint policy events. With this change, CloudTrail now logs all anonymous API requests made to external S3 buckets via VPC endpoints as CloudTrail network activity events and are delivered to the VPC endpoint owner's account. Anonymous API calls are requests made to an AWS service endpoint that do not include standard AWS authentication information, such as SigV4 signatures, IAM user credentials, or temporary security credentials. While most AWS services require authentication, some like S3 and SQS support anonymous access when explicitly configured for public websites.&nbsp;</em></p> 
<p><span style="font-style: italic;">CloudTrail network activity events enable VPC endpoint owners to record AWS API calls made using their VPC endpoints from a private VPC to AWS services. Network activity events provide visibility into resource operations performed within a VPC. For example, logging network activity events helps VPC endpoint owners detect when credentials from outside their organization&nbsp;attempt&nbsp;to access their VPC endpoints.&nbsp;</span></p> 
<p><span style="font-style: italic;">To learn more about CloudTrail network activity events, please&nbsp;</span><a href="https://docs.aws.amazon.com/awscloudtrail/latest/userguide/logging-network-events-with-cloudtrail.html%22%5D" style="font-style: italic;">refer to our&nbsp;documentation</a><span style="font-style: italic;">.&nbsp;</span></p> 
<p><span style="font-style: italic;">We thank <a href="https://www.varonis.com/varonis-threat-labs?hsLang=en">Varonis Threat Labs</a> for reporting this issue and collaborating with AWS."&nbsp;</span></p> 
<h2><strong>Mitigation&nbsp;strategies&nbsp;for&nbsp;evasive attacks</strong>&nbsp;</h2> 
<p>To&nbsp;reduce the risk of evasion attacks, we recommend the following:&nbsp;</p> 
<ol> 
 <li><strong>Restrict VPC Endpoint&nbsp;policies:&nbsp;</strong>Apply&nbsp;<strong>least privilege</strong>&nbsp;principles to VPC endpoint&nbsp;policies.&nbsp;Explicitly&nbsp;deny anonymous access and enforce IAM conditions for all requests&nbsp;</li> 
 <li><strong>Audit&nbsp;bucket&nbsp;policies&nbsp;regularly:&nbsp;</strong>Identify&nbsp;and remediate public or overly permissive bucket policies&nbsp;</li> 
 <li><strong>Enable alerts&nbsp;on&nbsp;policy&nbsp;changes:&nbsp;</strong>Set up notifications for any changes to VPC endpoint or bucket policies&nbsp;</li> 
</ol> 
<p>Continuously examining new services as a security researcher is essential — not only to understand their behavior, but also to uncover hidden risks and help ensure they are safer for everyone. We appreciate the immediate collaboration from the AWS Vulnerability Disclosure Program to limit this&nbsp;vulnerability's&nbsp;impact.&nbsp;&nbsp;</p> 
<p>Explore <a href="https://www.varonis.com/blog/tag/threat-research?hsLang=en">more Varonis Threat Labs research</a>.&nbsp;&nbsp;</p>  
<img alt="" height="1" src="https://track.hubspot.com/__ptq.gif?a=142972&amp;k=14&amp;r=https%3A%2F%2Fwww.varonis.com%2Fblog%2Fanonymous-s3-requests-evade-aws-logging&amp;bu=https%253A%252F%252Fwww.varonis.com%252Fblog&amp;bvt=rss" style="width: 1px!important;" width="1" />
