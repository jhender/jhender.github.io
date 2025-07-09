---
title: Unifi Network v2
excerpt: The next big upgrade
publishDate: 'Jul 9 2025'
isFeatured: false
tags:
  - tech
  - Unifi
  - Ubiquiti
  - wifi
  - 10G
  - network
---

## To faster speeds and beyond

<h3>

Network v1 when we moved into this house
- Router - Edgerouter Lite (which died and got replaced by:)
- Router - Unifi Security Gateway (USG) (1G, limited IDS processing)
- Access Point - UAP-AC-Pro (x2 units) (wifi 4, Wifi 5)
- Switch - Unifi Switch 24 (1G, non POE)
- ISP - ViewQwest 1 Gbps with static IP


# Pricing drops over the years have led to 3 Gbps plans being similar or slightly cheaper than previous gen 1 Gbps plans

Well then, if I am paying less, why not switch right?

At the same time Unifi also just released their UXG Fiber, which is a small unit that supports 10G routing, instead of having to use their wayyyy too big Dream Machine Pro/SE. This thing is now smaller, faster, more capable and has better ports. Wow.

Network v2
- Router - Unifi Gateway Fiber (UXG) 
- Access Point - Unifi U7 Pro (x2 units) (Wifi 6, Wifi 7)
- Switch - Unifi Switch 24 (1G, non POE) [no change]
- ISP - ViewQwest 3 Gbps with static IP


# UXG

![Packaging has really improved, super nice box](../assets/post5-uxgbox.jpg)
![Really nice finish](../assets/post5-uxg.jpg)
![The awesome ports](../assets/post5-uxgports.jpg)

![UXG](../assets/post5-uxgstats.png)

Look at those incredible ports.
1. It has proper 10G WAN
2. It can even support 10G SFP+ (in multiple)
3. It has multiple 2.5G LAN ports - perfect for supporting Wifi 6 and Wifi 7 at >1Gbps. Even one POE port!
4. It can actually support IDS/IPS at a high speed

# U7 Pro

![](../assets/post5-u7box.jpg)

I was deliberating between this and U6 series, since it's really quite enough speed, I don't have that many Wifi 7 devices, especially for the other people at home, and Wifi 7's 6 Ghz channels and other features were not fully mature and U7 had IOT issues initially.

But it was better this way because
- It's a super PITA to change out a ceiling AP
- I don't want to touch it again for yearssssss
- This means that it's overall cheaper to pay a bit more for U7 Pro and not labor charges again

![trying to remove the old AP](../assets/post5-removeap.png)
It's really tiring doing ceiling work, esp top of ceiling. Arms and shoulders aren't used to that length-of-time up.

![New bracket](../assets/post5_PXL_20250614_064919210.jpg)
New bracket is metal and really beautiful, compared to plain plastic old one

![trying to fit new AP into the wiring and trunking](../assets/post5_PXL_20250614_065910772.jpg)

![beautiful speedtest results on Pixel 8. 1764 Mbps](../assets/post5-speedtest.png)
Pretty awesome that I can get a speedtest result of 1700 Mbps at 6 Ghz 160 width. Wow, technically higher peak speeds than the 1G LAN ports. BUT LAN still trumps on many factors like stability, consistency, lower latency, no congestion on number of devices and neighbours. (My home LAN wiring is also upgradable to 2.5 or 10G if required)

# XGS PON

![](../assets/post5-selfinstall.jpg)

![](../assets/post-5-xgspon.jpg)

The just mail you the package and you do a self-swap, totally doable for me.
The fiber cable is a little tight and fiddly though, otherwise not a problem.

Biggest issue by far is
- Their handover from old to new ONT isn't great. I needed to call them to fix the routing. I suspect it's due to the new CGNAT and private IP implemented on the new ones. Total YUCKS.
- Good part is their technical support line was pretty responsive despite being 10 to 11pm
- They dropped my static IP for renewals, which was a !@$#@#@ as it means no external routing to me. YIKES. I neeeeeeed it for my Plex if nothing else. Tailscale and Cloudflare tunnels still have chance to work.
- Had to call again and request they give me back the static IP otherwise I can't survive.
- If you research, some of the ISPs give a floating IP, which is bearable, but CGNAT totally kills it. Still waiting to see if they are going to bill me, which I think they are. But overall pricing still ok, not any more than old pricing.

# Unifi Controller 9.2.87

It's so beautiful nowadays it's unimagiable. The sheer convenience and integration and data and display. Insane.

![details details details](../assets/post5-ui1.png)

![in graphical form](../assets/post5-ui2.png)

![beautifully reflecting the 2.5G and 10G connections](../assets/post5-ui3.png)

![](../assets/post5-ui4.png)

![lovely download speeds](../assets/post5-ui5.png)

Technically I could subscribe to the 10Gbps plans as well, but I really don't have the NAS, PC, or usb-c adapters to push 10Gbps to devices, nor even 2.5 Gbps to more ports. I don't think right now I want to get a 2.5 or 10G switch yet.

Let's see how it holds up when everyone is back home, and all the devices are re-enabled/re-deployed.

# Headaches on wiring

Because of the shifting of AP1's position to avoid the new cabinets, I had to 'extend' the wiring. Which meant a huge think and headache on how to do so as Cat6 cables aren't easily extended. End of the day I just plugged a new (hand crimped) cable into the other port and jiggled it into the casing and 1gang box.

I had to do a lot of back-and-forth testing of the cable terminations as I need to ensure it is crimped sufficiently well to not just support the full 1Gbps but even up to the 1.5+ Gbps that the new U7 Pro required. A lot of testing. AND the POE has to work as well. This is as much as we need to demand from the cable. 

![](../assets/post5-cable1.jpg)

![](../assets/post5-cable2.jpg)

Not very ideal but I think I managed to come to a compromise that's sufficiently fast and sufficiently tidy, using existing drops to new locations. 

End of the day, seeing incredible speedtest results and great connection speed is amazing. Haven't tested all the previous problematic corners but I think those are low traffic enough to be fine. 

I'd miss having a study table with a convenient LAN port point though. 

All in all, the gear was probably similarly priced to a Wifi 7 mesh system, but with better performance, but with much more difficult installation and flexibility. Saved a ton of $$$ by doing the wiring myself. Still will have most of my server/NAS/TV related stuff hardwired in. Potentially those can be grouped in a higher speed switch if I really need to in the future. Though I think 1 Gbps local should still be sufficient for Bluray high bitrate ATMOS etc.