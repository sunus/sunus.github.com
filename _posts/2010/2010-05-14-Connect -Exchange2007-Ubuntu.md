---
title: Connect Exchange 2007 using Evolution under Ubuntu
layout: post
---

I did a lot of Google search before, but failed. Then today morning my collegue told me that he found a way to connect the exchange server under Ubuntu. Here are the steps. 
1. sudo apt-get install evolution-mapi 
2. In Evolution -> Preferences -> Mail Accounts, add a new mail accout. 
3. Choose "Exchange MAPI" as Server Type, input your exchange server address and your username. 

That's it. This is so exciting that I can get rid of the OWA access.
