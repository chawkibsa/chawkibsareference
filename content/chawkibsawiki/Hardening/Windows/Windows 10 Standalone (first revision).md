*Second edition will contain more fine tuned controls based on organization's policies*
*Project ongoing ...*
## Account Policies
### Password Policy
### (L1) Ensure 'Enforce password history' is set to '24 or more password(s)' (Automated) #L1 #automated 
>Audit
![[Pasted image 20250802090300.png]]

> Remediation
![[Pasted image 20250802090420.png]]

### 1.1.2 (L1) Ensure 'Maximum password age' is set to '365 or fewer days, but not 0' (Automated) #L1 #automated 
	Don't set it to 0. If 0 then it will never expire
	Best practice: 365 days or fewer, but not 0
> Audit 
![[Pasted image 20250802090848.png]]

> Remediation
![[Pasted image 20250802090848.png]]

### 1.1.3 (L1) Ensure 'Minimum password age' is set to '1 or more day(s)' (Automated) #automated #L1
	If set to 0, then it will ask to change password immediately
	Best practice: 1 or more
> Audit
![[Pasted image 20250802091216.png]]

> Remediation
![[Pasted image 20250802091342.png]]

### 1.1.4 (L1) Ensure 'Minimum password length' is set to '14 or more character(s)' (Automated) #L1 #automated 
	Best practice: 14 or more

![[Pasted image 20250802091443.png]]

> Remediation
![[Pasted image 20250802091719.png]]

### 1.1.5 (L1) Ensure 'Password must meet complexity requirements' is set to 'Enabled' (Automated) #L1 #automated 
	When this policy is enabled, passwords must meet the following minimum requirements: 
		• Not contain the user's account name or parts of the user's full name that exceed two              consecutive characters 
		• Be at least six characters in length 
		• Contain characters from three of the following categories: 
			o English uppercase characters (A through Z) 
			o English lowercase characters (a through z) 
			o Base 10 digits (0 through 9) 
			o Non-alphabetic characters (for example, !, $, #, %) 
			o A catch-all category of any Unicode character that does not fall under the                       previous four categories. This fifth category can be regionally specific.
> Audit
![[Pasted image 20250802092232.png]]

> Remediation
![[Pasted image 20250802092557.png]]

### 1.1.6 (L1) Ensure 'Relax minimum password length limits' is set to 'Enabled' (Automated) #L1 #automated 
	Best practice: Enabled
*NOTE: This setting is only available within the built-in OS security template of Windows 10 Release 2004 and Server 2022 (or newer), and is not available via older versions of the OS, or via downloadable Administrative Templates (ADMX/ADML). Therefore, you must use a Windows 10 Release 2004 or Server 2022 system (or newer) to view or edit this setting with the Group Policy Management Console (GPMC) or Group Policy Management Editor (GPME)*
> Audit 
> Computer Configuration\Policies\Windows Settings\Security Settings\Account Policies\Password Policy\Relax minimum password length limits (see NOTE above)
![[Pasted image 20250802095612.png]]

>Remediation (Enabled)
> Computer Configuration\Policies\Windows Settings\Security Settings\Account Policies\Password Policy\Relax minimum password length limits (See NOTE above)
![[Pasted image 20250802095706.png]]

### 1.1.7 (L1) Ensure 'Store passwords using reversible encryption' is set to 'Disabled' (Automated) #L1 #automated 
	Note: Keeping the setting "Enabled" puts the user of potential credential harvesting attacks and decyption of his/her password. https://attack.mitre.org/techniques/T1556/005/
	Best practice: disabled

> Audit
![[Pasted image 20250802102002.png]]

> Remediation
![[Pasted image 20250802102053.png]]

---------------------------------------------------------------------------------
## 1.2 Account Lockout Policy
### 1.2.1 (L1) Ensure 'Account lockout duration' is set to '15 or more minute(s)' (Automated) #L1 #automated 
	If set to 0, the account will remain locked out until the administrator manually unlock it
	Best practice: 15 min 
> Audit
![[Pasted image 20250802102824.png]]

> Remediation
![[Pasted image 20250802102901.png]]

### 1.2.2 (L1) Ensure 'Account lockout threshold' is set to '5 or fewer invalid logon attempt(s), but not 0' (Automated) #L1 #automated
	If set to 0, then no lockout will be applied (not compliant to the above control as well)
	Best practice: 5 times or fewer
> Audit
![[Pasted image 20250802103135.png]]

> Remediation
![[Pasted image 20250802103205.png]]

### 1.2.3 (L1) Ensure 'Allow Administrator account lockout' is set to 'Enabled' (Manual) #L1 #manual
	Account Lockout Policy settings: Account lockout duration, Account lockout threshold, and Reset account lockout counter will be applied to local administrator.
	Best practice: enabled
> Audit
![[Pasted image 20250802103926.png]]
> Remediation
![[Pasted image 20250802104002.png]]

### 1.2.4 (L1) Ensure 'Reset account lockout counter after' is set to '15 or more minute(s)' (Automated) #L1 #automated 
	If "Not Defined", then after the lockout threshold time the administrator must manually reset users account password or unlock it
	Best practice: same as lockout time or less
>Audit 
![[Pasted image 20250802110911.png]]

>Remediation
![[Pasted image 20250802110941.png]]

--------------------------------------------------------------------------------
# Local Policies
## 2.1 Audit Policy 
*Explicitly blank (see benchmark)*
## 2.2 User Rights Assignment
### 2.2.1 (L1) Ensure 'Access Credential Manager as a trusted caller' is set to 'No One' (Automated) #L1 #automated 
	Best practice: No one
> Audit 
![[Pasted image 20250802113108.png]]

> Remediation
![[Pasted image 20250802113151.png]]

### 2.2.2 (L1) Ensure 'Access this computer from the network' is set to 'Administrators, Remote Desktop Users' (Automated) #L1 #automated 
	If Azure ATP or Ms DSA are in use, they should have the access as this computer from the network.
	Best practice: Administrators, Remote Desktop Users ONLY (see above).
> Audit
![[Pasted image 20250802114301.png]]

> Remediation
![[Pasted image 20250802114607.png]]

### 2.2.3 (L1) Ensure 'Act as part of the operating system' is set to 'No One' (Automated) #L1 #automated 
	Best practice: No One
> Audit
![[Pasted image 20250802114836.png]]

> Remediation
![[Pasted image 20250802114858.png]]

### 2.2.4 (L1) Ensure 'Adjust memory quotas for a process' is set to 'Administrators, LOCAL SERVICE, NETWORK SERVICE' (Automated) #L1 #automated 
	Best practice: Administrators, LOCAL SERVICE, NETWORK SERVICE.

> Audit
![[Pasted image 20250802115106.png]]

> Remediation
![[Pasted image 20250802115138.png]]

### 2.2.5 (L1) Ensure 'Allow log on locally' is set to 'Administrators, Users' (Automated) #L1 #automated 
	Best practice: Administrators, Users
> Audit 
![[Pasted image 20250802115430.png]]

> Remediation
![[Pasted image 20250802115522.png]]

### 2.2.6 (L1) Ensure 'Allow log on through Remote Desktop Services' is set to 'Administrators, Remote Desktop Users' (Automated) #L1 #automated 
	Best practice: Administrators, Remote Desktop Users.
> Audit 
![[Pasted image 20250802115803.png]]

> Remediation
![[Pasted image 20250802115833.png]]

### 2.2.7 (L1) Ensure 'Back up files and directories' is set to 'Administrators' (Automated) #L1 #automated 
	Best practice: Administrators
> Audit
![[Pasted image 20250802130806.png]]

> Remediation
![[Pasted image 20250802130841.png]]

### 2.2.8 (L1) Ensure 'Change the system time' is set to 'Administrators, LOCAL SERVICE' (Automated) #L1 #automated 
	Best practice: Administrators, LOCAL SERVICE.
> Audit 
![[Pasted image 20250802131219.png]]

> Remediation
![[Pasted image 20250802131246.png]]

### 2.2.9 (L1) Ensure 'Change the time zone' is set to 'Administrators, LOCAL SERVICE, Users' (Automated) #L1 #automated 
	Best practice: Administrators, LOCAL SERVICE, Users.
> Audit
![[Pasted image 20250802131445.png]]

Remediation
![[Pasted image 20250802131535.png]]

### 2.2.10 (L1) Ensure 'Create a pagefile' is set to 'Administrators' (Automated) #L1 #automated 
	Best practice: Administrators.
> Audit
![[Pasted image 20250802132117.png]]

> Remediation
![[Pasted image 20250802132230.png]]

### 2.2.11 (L1) Ensure 'Create a token object' is set to 'No One' (Automated) #L1 #automated 
	Best practice: No One
> Audit
![[Pasted image 20250802132620.png]]

>Remediation
![[Pasted image 20250802133000.png]]

### 2.2.12 (L1) Ensure 'Create global objects' is set to 'Administrators, LOCAL SERVICE, NETWORK SERVICE, SERVICE' (Automated) #L1 #automated 
	Best practice: Administrators, LOCAL SERVICE, NETWORK SERVICE, SERVICE.
> Audit
![[Pasted image 20250802164917.png]]

> Remediation
![[Pasted image 20250802164953.png]]

### 2.2.13 (L1) Ensure 'Create permanent shared objects' is set to 'No One' (Automated) #L1 #automated 
	Best practice: No One
> Audit
![[Pasted image 20250802165215.png]]

> Remediation
![[Pasted image 20250802165259.png]]

### 2.2.14 (L1) Ensure 'Create symbolic links' is set to 'Administrators' (Automated) #L1 #automated 
	Best practice: Administrators, and if Hyper-V is enabled, then NT VIRTUAL MACHINE\Virtual Machines.
> Audit
![[Pasted image 20250802165712.png]]

> Remediation (virtual box is enabled: needs this permission to operate)
![[Pasted image 20250802170321.png]]

### 2.2.15 (L1) Ensure 'Debug programs' is set to 'Administrators' (Automated) #L1 #automated 
	Best practice: Administrators
> Audit
![[Pasted image 20250802171447.png]]

> Remediation
![[Pasted image 20250802171516.png]]

### 2.2.16 (L1) Ensure 'Deny access to this computer from the network' to include 'Guests' (Automated) #L1 #automated 
	Best practice: Guests
> Audit
![[Pasted image 20250802171728.png]]

> Remediation
![[Pasted image 20250802171751.png]]

### 2.2.17 (L1) Ensure 'Deny log on as a batch job' to include 'Guests' (Automated) #L1 #automated 
	Best practice:
> Audit
![[Pasted image 20250802172102.png]]

> Remediation
![[Pasted image 20250802172126.png]]

### 2.2.18 (L1) Ensure 'Deny log on as a service' to include 'Guests' (Automated) #L1 #automated 
	This security setting does not apply to the System, Local Service, or Network Service accounts.
	Best practice: Guests

> Audit
![[Pasted image 20250802172729.png]]

> Remediation
![[Pasted image 20250802172803.png]]

### Ensure 'Deny log on locally' to include 'Guests' (Automated) #L1 #automated 
	If you apply this security policy to the Everyone group, no one will be able to log on locally.
	Best practice: Guests
> Audit
![[Pasted image 20250802183846.png]]

>Remediation
![[Pasted image 20250802183927.png]]

### 2.2.20 (L1) Ensure 'Deny log on through Remote Desktop Services' to include 'Guests' (Automated) #L1 #automated 
	Best practice: Guests
> Audit
![[Pasted image 20250802184216.png]]

> Remediation
![[Pasted image 20250802184256.png]]

### 2.2.21 (L1) Ensure 'Enable computer and user accounts to be trusted for delegation' is set to 'No One' (Automated) #L1 #automated 
	Best practice: No One
> Audit
![[Pasted image 20250802184753.png]]

> Remediation
![[Pasted image 20250802184820.png]]

### 2.2.22 (L1) Ensure 'Force shutdown from a remote system' is set to 'Administrators' (Automated) #L1 #automated 
	Best practice: Administrators
> Audit
![[Pasted image 20250802185220.png]]

> Remediation
![[Pasted image 20250802185243.png]]

### 2.2.23 (L1) Ensure 'Generate security audits' is set to 'LOCAL SERVICE, NETWORK SERVICE' (Automated) #L1 #automated 
	Best practice: LOCAL SERVICE, NETWORK SERVICE.
> Audit
![[Pasted image 20250802185518.png]]

> Remediation
![[Pasted image 20250802185600.png]]

### (L1) Ensure 'Impersonate a client after authentication' is set to 'Administrators, LOCAL SERVICE, NETWORK SERVICE, SERVICE' (Automated) #L1 #automated 
	Best practice: Administrators, LOCAL SERVICE, NETWORK SERVICE, SERVICE.
> Audit
![[Pasted image 20250802191919.png]]

> Remediation
![[Pasted image 20250802191944.png]]

### 2.2.25 (L1) Ensure 'Increase scheduling priority' is set to 'Administrators, Window Manager\Window Manager Group' (Automated) #L1 #automated 
	Best practice: Administrators, Window Manager\Window Manager Group.
> Audit
![[Pasted image 20250802193353.png]]

> Remediation
![[Pasted image 20250802193428.png]]