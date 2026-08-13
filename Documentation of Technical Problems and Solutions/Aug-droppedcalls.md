Problem:
Users report intermittent dropped VoIP calls and calls routing to voicemail.

Environment:
Yealink phones → phone-only switch → DrayTek Vigor 2926 → Ziply Fiber
Separate voice subnet: 192.168.100.0/24
Separate public IP: 50.45.157.122

Impact:
Critical telecommunication unreliability, causing disruption with production line and intake of cases.

Troubleshooting:
- Rebooted Vigor; issue persisted.
- Verified SIP ALG disabled.
- Monitored VoIP QoS statistics.
- Healthy test call showed 20 ms RTP packetization, 0 jitter, 0% loss.
- Bypassed DrayTek and connected phone switch to main router.
- Phones reacquired DHCP leases on 192.168.193.0/24 after reboot.
- Tested two endpoints through phone switch: ~900/450 Mbps.
- Continued monitoring production calls.

Root Cause:
**Pending** / suspected DrayTek or dedicated WAN path.

Resolution:
Temporary bypass of DrayTek.

Verification:
Calls stable after topology change; voicemail behavior normal.

Next Steps:
Monitor for recurrence. If issue returns, capture SIP/RTP traffic.