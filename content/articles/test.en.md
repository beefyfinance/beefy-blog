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

**TL;DR**: After explaining to the Grim team why they needed to take action due to an outstanding smart contract exploit, Beefy devs showed Grim how to whitehat hack and preserve $320,000 of remaining funds. **The whitehat hack occurred after a slow and inadequate response from the Grim team and seeing a hacker exploit a substantial fraction of the platform’s $32 million TVL.**

The Grim team’s accusation of Beefy implementing a malicious attack is unfounded, as the whitehat-hack contract address was shared with their team **before the blackhat attack took place**. Grim already had knowledge from Beefy of the possible exploit but did not act on this information. This left the task of securing funds up to Beefy.

These rescued funds were swapped from altcoins to stables and blue chips to hold value. Beefy has been waiting for a reputable third party to find that no inside exploit occurred before returning the funds to Grim.

Beefy’s intention remains to return these funds to rightful owners. We have requested the assistance of The Fantom Foundation to this end.

### Beefy's whitehat response

Beefy Finance is a security-first platform. Preserving user safety is key to bringing DeFi forward. Beefy insists that every project it interacts with provides reliable, correct code and ensures safety measures are taken. We consistently go out of our way to protect users even on competing platforms. One recent example is the Grim Finance exploit on December 18, 2021.

However, the recent accusation emanating from Grim’s ranks of Beefy stealing funds is categorically false. Grim Finance is a fork of Beefy Finance, and the code that was exploited on December 18 was code that Grim itself added for an unknown reason. Beefy worked overtime to inform Grim of the exploit and urged that Grim pause its vaults to protect users. Grim’s response was slow and inadequate and allowed $32 million of user value to be stolen.

Discussions at the time on publicly stating Beefy’s part in addressing the incident were debated and decided against. Beefy’s role here was to protect users and their funds, not to provide behind-the-scenes information that could be interpreted as greater FUD than the exploit itself. Since the incident, the preserved funds have waited in Beefy’s named public treasury wallet. Regular daily business at Beefy has continued, and no further contact from Grim was received regarding this irregular situation before February 20, 2022.

### Timeline

**December 18, 2021**

**7:12 UTC**: The BSC protocol Charge DeFi is exploited. The timeline table of Charge DeFi’s response may be seen below ([https://chargedefi.medium.com/chargedefi-security-incident-1fcc134392f0](https://chargedefi.medium.com/chargedefi-security-incident-1fcc134392f0 "https://chargedefi.medium.com/chargedefi-security-incident-1fcc134392f0")).

**Note how Grim Finance was notified as early as 9:58 UTC of the situation.**  
![](/uploads/table.png)

**8:27 UTC**: An alert is posted in Beefy’s Discord by a Beefy moderator that Charge Defi has been hacked. In the ensuing hours, Beefy pieces together that Charge Defi’s code is a fork of Grim Finance’s and that Grim’s is a fork of Beefy Finance’s.  
![](/uploads/1-1.png)

Beefy’s first order of business is to determine whether the matter affects the Beefy platform. We determined that it does not, simply because the exploited code section is not present in Beefy’s contracts. The precise form of the exploit takes time to trace out, and doing so is not urgent because the hack does not impact Beefy.

**16:00 UTC**: Moonster (Beefy Dev) examined the matter and determines that the exploit used code introduced by Grim Finance.

![](/uploads/2.png)

Grim’s vulnerability is owed to the Solidity function below. This function requires the caller to pass the address of a contract, unconcerned that that contract could be malicious. The function calls _safeTransferFrom()_ on this passed contract, but a malicious contract may call again (“re-enter”) _depositFor()_. By recursively nesting this way a few times a blackhat may mint 10x or 100x the amount of shares than it has rights to.  
  
![](/uploads/3-1.png)

**17:28 UTC**: Weso (Beefy Lead Dev) reaches out to Grim through Discord. Weso notifies LUT (Grim mod) of the exploit and asks to set up a group to discuss details.

**17:30 UTC**: LUT states that Grim “devs had a look when reports started pouring - 7 hours ago.” So Grim should have been fully aware of their situation.  
![](/uploads/4.png)

**17:40 UTC**: An advanced blackhat attacker starts exploiting Grim Finance. [https://ftmscan.com/address/0xdefc385d7038f391eb0063c2f7c238cfb55b206c](https://ftmscan.com/address/0xdefc385d7038f391eb0063c2f7c238cfb55b206c "https://ftmscan.com/address/0xdefc385d7038f391eb0063c2f7c238cfb55b206c")

**17:53 UTC**: Discord group chat is set up between the Beefy and Grim dev teams. Beefy’s devs immediately detail the nature of the problem and explain that all Grim vaults must be urgently secured. Specifically, vaults should be paused to prevent them from performing transactions like the drainage of funds.

**17:57 UTC**: Weso mentions that Kexley (Beefy’s Chief Strategist) is developing an exploit whitehat-hack contract to demonstrate the problem as an aid to Grim.

**18:40 UTC:** Kexley, finished writing the example exploit contract to prove Moonster’s points, and asks Grim to “please pause all your vaults,” indicating that all of Grim’s user funds are at risk. Grim agrees and starts the process. **Kexley additionally provides Grim with the whitehat-hack contract address and links to the contract’s first transaction that proving the exploitable reentrancy flaw.**  
![](/uploads/5.png)

Before Kexley completed the example whitehat exploit, a blackhat had already deployed and activated its own, more advanced exploit contract. Grim identified the attacker’s address at  
[https://ftmscan.com/address/0xdefc385d7038f391eb0063c2f7c238cfb55b206c](https://ftmscan.com/address/0xdefc385d7038f391eb0063c2f7c238cfb55b206c "https://ftmscan.com/address/0xdefc385d7038f391eb0063c2f7c238cfb55b206c"). The blockchain shows that the attacker began the exploit an hour before Kexley completed the whitehat-exploit contract. Only once Beefy showed Grim that the exploit could be done did Grim start safety measures (vault pauses), at 19:00 UTC.

Soon after, Kexley checks in and notices the attack still unfolding and that Grim’s response has been slow and inadequate. He decides to proactively target an unprotected vault with the proof code Beefy developed in order to preserve user funds sitting there. **In other words, Kexley implements a whitehat hack to help preserve the integrity of Fantom DeFi using the same contract shared previously.**

Minimal funds (less than $3,000) were recovered on this first whitehat attempt. The next day, Kexley checks again and finds numerous vaults still unprotected and spends three hours continuing the whitehat hack. A large amount of the funds Kexley preserves are in unstable form and since he knows that a post mortem will take weeks or months to complete, he converts the unstable altcoin into stables and blue chips in order to preserve value.

Timings of Kexley’s whitehat maneuvers may be verified in the whitehat-exploit contract here [https://ftmscan.com/address/0x9c7c5af937f53340314ac244b39c96fe71fb646d](https://ftmscan.com/address/0x9c7c5af937f53340314ac244b39c96fe71fb646d "https://ftmscan.com/address/0x9c7c5af937f53340314ac244b39c96fe71fb646d").