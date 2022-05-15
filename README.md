# OPNSense


### 🤝 How to install DDNS Cloudfare 

  # Cloudflare side
 - Login into your Cloudflare account, select your profile from the right hand corner & select API Tokens 
 - Create an API Token -> Edit Zone DNS - Use Template -> Zone Resource - select your domain - > Continue to summary -> Create Token
 - Go to your domain -> DNS -> Add an A Record, name (for example ddns, this is the one in front of your domain), IPv4 address: 1.1.1.1 -> Proxy Status: **OFF** -> Save

  # OPNSense side
 - Please refer to the link (https://docs.opnsense.org/manual/dynamic_dns.html) for the plugin install
 - Once that's installed, go to Services -> Dynamic DNS -> General Settings -> Ensure it's "Enabled"
 - Back to the Accounts tab -> ADD -> 
 -    Service: Cloudflare
 -    Username: myname@gmail.com (Use your Cloudflare email address)
 -    Password: Cloudflare Global API Key ( Keep that secure like you would with your password )
 -    Zone: amazon.com (use your domain)
 -    Hostname: ddns.amazon.com ( In this case, the hostname is the dns record from cloudflare)
 -    Check IP method: Interface ( This monitors the interface)
 -    Force SSL: enabled
 -    Interface to Monitor: WAN 
 -    Description: Whatever you like

# That's it. Give it a few minutes for the records to update and the world will know your IP. 

