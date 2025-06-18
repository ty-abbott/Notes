Debug mode is necessary when getting stuff out of memory. 
sekurlsa::logonpasswords gets passwords and hashes out of LSASS. Either current or recently logged in users. TTL for creds is 30 seconds after logoff. 
Administrator privileges are needed for mimikatz effectiveness. 

How to protect against mimikatz -
- dont let accounts be local administrators/domain administrators.
- You can disable credentials from being stored in memory with a registry update of HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\SecurityProviders\WDigest
UseLogonCredential, set to 0
- Disable debug mode for all local administrators on desktops and servers.
- Enable LSA protection (RunAsPPL registry key) This does have potential to break things
- Disable storage of plain text passwords in AD
- Disable password caching

  - Note that this might mess things up for people with laptops, who will want to login while away from the office.
  - You can set up your VPN client to force a VPN connection before login, but that'll of course cause you headaches if you need to authenticate to a wireless hotspot first.
  -  Often that is mitigated by telling people to allow tethering to their cellphone, and then in written policies and technical controls forbid the use of free/public hotspots such as hotel or coffee shop wifi.
  -  This is a simple and effective mitigation, but it needs some thought and communication in advance to make it work in many organizations.
  -  Credential guard
  -  protected user groups
