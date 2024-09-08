## Windows Domain lab

### Intro 
I am creating a windows domain at home to use for learning and (possibly more important) breaking. The purpose of the lab is three fold
- First, so that I can learn more about domain administration. With my current job as a security engineer we advise customers with their windows domains
all of the time. For things that I am a bit unfamiliar with, I want a place that I can get my hands dirty implementing the security controls that we advise.
- Second, I want a place where I can try out common(and uncommon) windows exploits eg kerberoasting, NTLM Relay, AD attacks, etc. I know them all in theory but I want
to get to know them more in practice.
- Third, I spent a lot of hours learning various skills for windows domains through sys admin work and I dont want it to blow away in the winds of time and unuse.

### Setup 
Pretty simple stuff overall:
- virtual box as the hypervisor. It wont be on all the time and it will share live on my desktop. Virtual box is free and good. I will put networking in NAT.
Host will be gateway and domain controller will be everything else.  
- server 2022 as a domain controller. DNS, DHCP, AD, GPMC, all that good stuff will be on their.
- another server 2022 as an IIS server. Will put random services running on it. The services will change depending on the day. 
- windows 10 workstation
- for attacking the windows domain I will hop on my kali box and ensure that it can communicate with the other machines and can join to domain with samba when needed.

 ### Ventures 
 As I continue to work on it and implement new things - I am going to document it on this page and will write down the topics that I learn throughout this site. 

 #### Creating the domain
 - I created a NAT network on virtual box
 - For now I am going to create static IPs. If I want DC to handle DHCP then I will just turn off DHCP in the NAT network -> give dc static -> set
set other machines to dhcp server being windows dc
- I had a problem with setting up the static IP - because I changed the dhcp setting on virtualbox while dhcp was configured it caused the ip to be cached.
- Also for virtual box .1-.3 are reserved for gateway and dhcp - i was changing to .2 and was getting internet connectivity problems.
- When joining to the domain it is really important that the Domain DNS server is configured as one of the local dns servers. I am sure you can probably just
  use IP but I didnt know how.
- also windows 10 home edition cannot be domain joined only professional or enterprise
