---
title: "Feeding Frenzy: RCE on Azure Cosmos for PostgreSQL"
url: "https://www.varonis.com/blog/rce-on-azure-cosmos-for-postgresql"
date: "Mon, 11 May 2026 14:26:18 GMT"
author: "Coby Abrams"
feed_url: "https://www.varonis.com/blog/feed/"
---
Varonis Threat Labs uncovered a vulnerability in Azure Cosmos for PostgreSQL, leading to remote code execution (RCE). Due to an improperly validated server configuration value, it was possible to edit arbitrary PostgreSQL configurations through the Azure management API, including those managed by Azure and controlling sensitive server functions.
