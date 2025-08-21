# 🌐 Cloudflare DDNS Updater

A lightweight **Bash script** to keep your **Cloudflare DNS A record** updated with your machine’s current private IP address.  
Perfect for **home labs, self-hosted services, or servers with dynamic IPs**.

---

## Features
- 🌍 Updates Cloudflare **A records** automatically
- 🔄 Detects your current IP from a chosen network interface
- ⏱️ Configurable TTL for DNS records

---

## How It Works
1. Fetches the current IP address from your network interface (default: `eth0`)
2. Queries the Cloudflare API for the matching A record
3. If the IP has changed, updates the DNS record

---

## Usage
1. Clone or download this repo.
2. Edit the script variables at the top:

   ```bash
   auth_email="your-email@example.com"
   auth_method="token"       # "global" for Global API Key or "token" for Scoped API Token
   auth_key="your-api-key-or-token"
   zone_identifier="your-zone-id"
   record_name="your.domain.com"
   eth_int="eth0"            # network interface to monitor
   ttl=3600
   proxy="false"

3. Add to cron (run every 5 minutes):
   
   */5 * * * * /path/to/cloudflare_ddns.sh
