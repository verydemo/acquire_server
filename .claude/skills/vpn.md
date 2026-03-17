# Start Cloudflare Tunnel VPN

启动 Cloudflare Tunnel 代理节点，获取 VLESS 链接。

## Usage

When user says:
- "start vpn"
- "启动vpn"
- "开启代理"
- "cloudflare tunnel"
- "cf proxy"

## Instructions

1. Run the GitHub Actions workflow:
   ```bash
   cd /Users/zhangjl/code/proj/work/acquire_server && gh workflow run cloudflare-tunnel-proxy.yml -f proxy_mode=vless -f cf_tunnel_mode=quick
   ```

2. Wait a few seconds and get the run URL:
   ```bash
   gh run list --workflow=cloudflare-tunnel-proxy.yml --limit 1
   ```

3. The VLESS link will be sent to DingTalk automatically.

## Parameters

- `proxy_mode`: `vless` (default) or `ss` (Shadowsocks)
- `cf_tunnel_mode`: `quick` (default, no CF account needed) or `named` (requires CF_TUNNEL_TOKEN secret)
- `duration`: Keep-alive hours (default: 5)

## Manual trigger with custom params

```bash
gh workflow run cloudflare-tunnel-proxy.yml -f proxy_mode=vless -f cf_tunnel_mode=quick -f duration=8
```