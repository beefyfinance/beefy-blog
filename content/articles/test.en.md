+++
date = 2022-02-21T03:00:00Z
draft = true
header_image = "/uploads/title2.png"
short_description = "Incident Report"
sub_header = "Incident Report: Grim Holiday Hack, Beefy Whitehat Response"
title = "Incident Report: Grim Holiday Hack, Beefy Whitehat Response"

+++
  
![](https://lh6.googleusercontent.com/yyK5_Mq48pN2y8oNbHMKVXZutr_HnNLKdAjMSQfNLYYOXBX6m9CEFUVw2ML3QKBOSFZI_8_Qh66h9s2PQkrdA590_zuNHRb4-Rrg3YwkdICXLYNyQ9P2GuXTA1eH88egwTOYRFVj =624x351)

### Summary

**TLDR: After explaining to the Grim team why they needed to take action to save user funds, and after watching a slow and inadequate response and seeing a hacker exploit a substantial fraction of the platform’s TVL, $32 million, Beefy devs showed Grim how to whitehack and so preserve the funds that remained, $320 thousand. These funds were swapped from altcoins to stables and bluechips in order to hold value. Beefy has been waiting for a reputable third-party finding that no inside exploit occurred before returning funds to Grim. Beefy’s intention remains to return these funds to rightful owners. We have requested the assistance of The Fantom Foundation to this end.**  
  
Beefy Finance is a security-first platform. Preserving user safety is key to bringing DeFi forward. Beefy engages every project it interacts with to correct code and ensure safety measures are taken. Beefy consistently goes out of its way to protect users even on competing platforms. An example took place on December 18, 2021 as Grim Finance was exploited. The recent accusation emanating from Grim’s ranks of Beefy stealing funds is completely false. Grim Finance is a fork of Beefy Finance, and the code that was exploited on December 18 was code that Grim itself added. Beefy worked overtime to inform Grim of the exploit, and urged that Grim pause its vaults to protect users. Grim’s response was slow and inadequate and allowed $32 million of user value to be stolen.

Discussions at the time about publicly stating Beefy’s part in addressing the incident were debated, and decided against. Beefy’s role here was to protect users and their funds, not to provide behind the scenes information that could be interpreted as greater FUD than the exploit itself. Since the incident, daily business at Beefy has continued and no further contact from Grim had been received prior to February 20, 2022.

###   
Timeline

**December 18, 2021**

**7:12 UTC**: The BSC protocol Charge DeFi is exploited. The timeline table of Charge DeFi’s response may be seen below ([https://chargedefi.medium.com/chargedefi-security-incident-1fcc134392f0](https://chargedefi.medium.com/chargedefi-security-incident-1fcc134392f0 "https://chargedefi.medium.com/chargedefi-security-incident-1fcc134392f0")).  
  
Note how Grim Finance was notified as early as 9:58 UTC of the situation.  
![](/uploads/table.png)

**8:27 UTC**: An alert is posted in Beefy’s Discord by a Beefy moderator that Charge Defi has been hacked. In the ensuing hours Beefy pieces together that Charge Defi’s code is a fork of Grim Finance’s and that Grim’s is a fork of Beefy Finance’s.  
![](/uploads/1-1.png)

Beefy’s first order of business is to determine whether the matter affects Beefy’s platform. It is determined that it does not, simply because the exploited code section is not present in Beefy’s contracts. The precise form of the exploit takes time to trace out, and doing so is not urgent because the hack does not impact Beefy.

  
**16:00 UTC**: Moonster (Beefy Dev) examined the matter and determines that the exploit used code introduced specially by Grim Finance.

![](/uploads/2.png)

Grim’s vulnerability owed to the function below. This function requires the caller to pass the address of a contract, not considering that that contract could be malicious. The function calls safeTransferFrom() on this passed contract, but a malicious contract may re-enter depositFor(). By recursively nesting this a few times a blackhat may mint 10x or 100x the amount of shares than it has rights to.  
![](https://lh3.googleusercontent.com/2nj5QZoItEIyy_3FFzbSJL0i82jGz-g_e1vHEhh3Ungh2wFiw6_AdwoAj9zmJuk_QVkpCEe3OiLusw3O9UoKshugNTVecn4WmZ8FWGXuDQZF5yPdCQKxDOqDBidnq5GREnhs-Iun =622x279)

17:28 UTC: Weso (Beefy Lead Dev) reaches out to Grim through Discord. Weso notifies LUT (Grim mod) of the exploit, and asks to set up a group to discuss details.  
  
17:30 UTC: LUT states that Grim “devs had a look when reports started pouring - 7 hours ago.” So Grim should have been fully aware of their situation.  
  
![](https://lh6.googleusercontent.com/WJ7OiOsrnrpRzMceZfWYGONeHnlC6exfL4jGIzGnVHEHe0J7DRu7e_ukT9WNNL1SPY-M_Jbvq2mSjAqHtHjidag-g85osD6UP_rfggXvLvO1A0aj_Bh_ybNYZapP1M9D7cWhH7pL =624x327)

17:40 UTC: An advanced blackhat attacker starts exploiting Grim Finance. [https://ftmscan.com/address/0xdefc385d7038f391eb0063c2f7c238cfb55b206c](https://ftmscan.com/address/0xdefc385d7038f391eb0063c2f7c238cfb55b206c "https://ftmscan.com/address/0xdefc385d7038f391eb0063c2f7c238cfb55b206c")

17:53 UTC: Discord group chat is set up between the Beefy and Grim dev teams. Beefy’s devs immediately detail the nature of the problem and explain that all Grim vaults must be urgently secured. Specifically, vaults should be paused to prevent them from performing transactions, like drainage of funds.  
  
17:57 UTC: Weso mentions that Kexley (Beefy’s Chief Strategist) is developing an exploit contract to demonstrate the problem as an aid to Grim.  
  
18:40 UTC: Kexley, finished writing the example exploit contract to prove Moonster’s points, asks Grim to “please pause all your vaults,” indicating that all of Grim’s user funds are at risk. Grim agrees and starts the process.

![](https://lh5.googleusercontent.com/411VJtm3xE2XJ2-EOQUBuWpff0fF5vnEIqQZsNLiuDfsoj3JODjJ8V1x_wkxLjXrEpIJSQd0F6I9tbeeYjo9lB9PROEfg5mAejfZ7lXIjijgWQJK67_7HB5kzVh85BQ2bj_UY3ly =624x289)

Before Kexley completed the example whitehat exploit, a blackhat had already deployed and activated its own, more advanced exploit contract. Grim identified the attacker’s address at  
[https://ftmscan.com/address/0xdefc385d7038f391eb0063c2f7c238cfb55b206c](https://ftmscan.com/address/0xdefc385d7038f391eb0063c2f7c238cfb55b206c "https://ftmscan.com/address/0xdefc385d7038f391eb0063c2f7c238cfb55b206c"). The blockchain shows that the attacker began the exploit an hour before Kexley completed the whitehack-exploit contract. Only once Beefy showed Grim that the exploit could be done did Grim start safety measures (vault pauses), at 19:00 UTC.

Soon after, Kexley checks in and notices the attack still unfolding and that Grim’s response has been slow and inadequate. He decides to proactively target an unprotected vault with the proof code Beefy developed in order to preserve user funds sitting there. In other words, he implements a whitehack to help preserve the integrity of Fantom DeFi. Minimal funds (less than $3,000) were recovered on this first whitehat attempt. The next day, he checks again and finds numerous vaults still unprotected, and so spends three hours to continue the whitehack. A large amount of the funds he preserves are in unstable form and since he knows that a post mortem will take weeks or months to complete, he converts the unstable altcoin into stables and bluechips in order to preserve value.

Timings of Kexley’s whitehat maneuvers may be verified in the whitehack-exploit contract here [https://ftmscan.com/address/0x9c7c5af937f53340314ac244b39c96fe71fb646d](https://ftmscan.com/address/0x9c7c5af937f53340314ac244b39c96fe71fb646d "https://ftmscan.com/address/0x9c7c5af937f53340314ac244b39c96fe71fb646d").