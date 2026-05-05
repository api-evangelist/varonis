---
title: "Meet Bluekit: The AI-Powered All-in-One Phishing Kit"
url: "https://www.varonis.com/blog/bluekit"
date: "Wed, 29 Apr 2026 13:00:00 GMT"
author: "Daniel Kelley"
feed_url: "https://www.varonis.com/blog/rss.xml"
---
<p>At one point in time, the phishing kit market was specialized. Operators bought a credential-harvesting page from one seller, a domain rotator from another, and an SMS gateway from a third. Then they stitched the rest together on their own infrastructure.</p>  
<p><a href="https://www.varonis.com/varonis-threat-labs?hsLang=en">Varonis Threat Labs</a> recently discovered Bluekit, a new phishing kit pitching a broader model. It advertises 40+ website templates, automated domain purchase and registration, 2FA support, spoofing, geolocation emulation, Telegram and browser notifications, antibot cloaking, and add-ons like an AI assistant, voice cloning, and a mail sender.</p> 
<p>The templates we reviewed covered email and cloud accounts, developer platforms, social media, retail, and crypto services, including iCloud, Apple ID, Gmail, Outlook, Hotmail, Yahoo, ProtonMail, GitHub, Twitter, Zoho, Zara, and Ledger.</p> 
<h2><strong>What Bluekit ships in one panel</strong></h2> 
<p>To see how that held up in practice, we obtained access to Bluekit and reviewed the kit from the inside. That gave us a closer look at the operator dashboard, the site-creation flow, the post-capture panels, and the AI Assistant.</p> 
<p>Bluekit pulls several parts of the phishing workflow into one place. The panel covers site creation, domain setup, captured logs, delivery tooling, and campaign support features, with Telegram wired in as the default exfiltration channel.</p> 
<p>Operators can buy or connect domains from the same interface used to manage phishing pages and captured logs, rather than splitting that work across separate services.</p> 
<p>That setup flow also extends into site creation itself. In the view we reviewed, operators could pick a domain, choose a mode, and select from a broad list of target brands and services, including consumer email providers and developer-facing platforms.</p> 
<p>Bluekit also exposes fairly granular control over how a site behaves once it is live. In the site-edit view we reviewed, the kit exposed login-detection actions, redirect behavior, anti-analysis checks, spoofing options, and device&nbsp;filters from the same configuration panel.</p> 
<p>Those configuration views also exposed proxy settings and site-level checks tied to how sessions were handled after login. That gives the operator more control over what happens once a target leaves the phishing page.</p> 
<p>In the Mammoth Details view we reviewed, Bluekit tracked session state, stored repeated dumps of cookies and local storage, and kept a live view of what the target saw after login. That shows the kit is handling more than a basic credential grab, with the panel also surfacing session data after login.</p> 
<h2><strong>The AI Assistant under the hood</strong></h2> 
<p>We were especially interested in the AI component. Inside Bluekit, the AI Assistant has its own panel and exposes multiple model options, including an abliterated Llama default alongside GPT-4.1, Claude Sonnet 4, Gemini, and DeepSeek variants.</p> 
<p>In our testing, we were only able to use the default abliterated Llama model. The commercial options appeared in the interface, but they required additional configuration we did not have.&nbsp;</p> 
<p>Even so, their presence is still notable. If those models are usable in practice, they are likely being accessed through jailbroken or otherwise permissive instances, because a standard setup would be more likely to block or censor this kind of output.</p> 
<p>We used a detailed campaign brief built around an executive phishing scenario: a Microsoft 365 MFA re-verification lure aimed at the CISO of "BlueKit Software," with a branded QR code, a polished email delivery path, and a credential-harvesting login page as the end goal.</p> 
<p>We expected something closer to a polished phishing copilot: a finished lure, cleaner email copy, and perhaps even a workable QR-driven flow with less manual effort. What we received was much more limited. The assistant returned a structured campaign draft, and much of it relied on placeholders instead of content that looked ready to use as-is.</p> 
<p>In close-up, the limitation is easier to see. The draft included a useful structure, but it still depended on generic link fields, placeholder QR blocks, and copy that would need cleanup before use. Bluekit’s AI Assistant looked more like a way to generate a campaign skeleton than a finished phishing flow.</p> 
<div class="wistia_responsive_padding" style="padding: 47.5% 0 0 0;"> 
 <div class="wistia_responsive_wrapper" style="height: 100%; width: 100%;"> 
  <div class="hs-responsive-embed-wrapper hs-responsive-embed" style="width: 100%; height: auto; overflow: hidden; padding: 0; margin: 0px auto; display: block;"> 
   <div class="hs-responsive-embed-inner-wrapper" style="overflow: hidden; padding-bottom: 56.25%; margin: 0;">
    
   </div> 
  </div> 
 </div> 
</div>  
<h2>&nbsp;</h2> 
<h2><strong>Where Bluekit fits in the ecosystem</strong></h2> 
<p>Bluekit has been on our radar for a while. Early on, part of the goal was to see whether we could catch the kit in a live campaign. Over time, though, the release cadence became part of the story. The developer kept shipping new features and adding templates quickly enough that keeping up with the changes became just as important as waiting for a single live sample.</p> 
<p>&nbsp;</p> 
<p>Compared with similar phishing kits that have already advanced further into automation and operator convenience, Bluekit still appears to be a kit in active development. The feature set keeps evolving as we track it, and if that pace continues with broader adoption, Bluekit is likely to surface in future campaigns.</p> 
<div class="wistia_responsive_padding" style="padding: 50.21% 0 0 0;"> 
 <div class="wistia_responsive_wrapper" style="height: 100%; width: 100%;"> 
  <div class="hs-responsive-embed-wrapper hs-responsive-embed" style="width: 100%; height: auto; overflow: hidden; padding: 0; margin: 0px auto; display: block;"> 
   <div class="hs-responsive-embed-inner-wrapper" style="overflow: hidden; padding-bottom: 56.25%; margin: 0;">
    
   </div> 
  </div> 
 </div> 
</div>  
<br />
<br /> 
<p>&nbsp;</p> 
<p>Stay up to date on the threat landscape by following <a href="https://www.varonis.com/varonis-threat-labs?hsLang=en">Varonis Threat Labs</a>.</p>  
<img alt="" height="1" src="https://track.hubspot.com/__ptq.gif?a=142972&amp;k=14&amp;r=https%3A%2F%2Fwww.varonis.com%2Fblog%2Fbluekit&amp;bu=https%253A%252F%252Fwww.varonis.com%252Fblog&amp;bvt=rss" style="width: 1px!important;" width="1" />
