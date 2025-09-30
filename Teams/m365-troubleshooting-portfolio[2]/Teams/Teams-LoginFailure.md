# Issue: Teams Login Failure (Error Code: CAA20004)

**Date Logged:** 30-09-2025  
**Service Area:** Microsoft Teams  

---

### Symptoms  
- User unable to sign in to the Teams desktop app.  
- Error code displayed: `CAA20004`.  
- Web version of Teams works fine.  

### Root Cause  
Cached credentials in the Teams desktop client were corrupted.  

### Resolution Steps  
1. Sign out of the Teams desktop app.  
2. Close Teams completely (right-click the icon in the system tray → Quit).  
3. Navigate to `%appdata%\Microsoft\Teams`.  
4. Delete all files and folders in that directory.  
5. Restart the computer.  
6. Launch Teams and sign in with the user’s credentials.  

### Verification  
- User was able to sign in successfully after cache was cleared.  
- Teams sync and chat features worked without further errors.  

### PowerShell Check (Optional)  
```powershell
Get-CsOnlineUser -Identity user@domain.com
```

---

**Status:** ✅ Resolved
