# Issue: Poor Call Quality in Microsoft Teams

**Date Logged:** 30-09-2025  
**Service Area:** Microsoft Teams  

---

### Symptoms  
- User reported choppy audio and frequent call drops during Teams meetings.  
- Video intermittently froze.  
- Issue persisted across multiple calls.  

### Root Cause  
Network bandwidth was insufficient, and QoS (Quality of Service) settings were not applied on the corporate network.  

### Resolution Steps  
1. Verified user’s device met Teams hardware requirements.  
2. Checked Teams call analytics: confirmed packet loss and jitter.  
3. Ran network speed test (download and upload below recommended thresholds).  
4. Coordinated with network team to:  
   - Apply QoS for Teams traffic (UDP 3478–3481).  
   - Increase available bandwidth.  
5. Guided user to switch from Wi-Fi to wired connection for stability.  

### Verification  
- After adjustments, Teams call diagnostics showed stable latency and minimal packet loss.  
- User confirmed calls were clear and uninterrupted.  

### PowerShell Check (Optional)  
```powershell
Get-CsUserSession -User user@domain.com
```

---

**Status:** ✅ Resolved
