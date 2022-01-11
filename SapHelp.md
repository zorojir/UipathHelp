This information might help us for configuring SAP Logon and Client side scripting on a Golden Image:
SAP Logon Configuration will be stored on user login basis in C:\Users\<userName>\AppData\Roaming\SAP\Common\SAPUILandscape.xml. so, make sure you have a code to copy the SAPUILandscape.xml(which has all details about connections) to the above folder
Enabling Client Side Scripting is also done on user login basis
Enable Scripting [HKEY_CURRENT_USER\Software\SAP\SAPGUI Front\SAP Frontend Server\Security] “UserScripting” (REG_ DWORD) [Default: ”1”] {0 = inactive; 1 = active } This option has to be activated to be able to activate the two options mentioned below.
Notify when a script attaches to SAP GUI [HKEY_CURRENT_USER\Software\SAP\SAPGUI Front\SAP Frontend Server\Security] “WarnOnAttach” (REG_DWORD) [Default: ”1”] {0 = inactive; 1 = active }
Notify when a script opens a connection [HKEY_CURRENT_USER\Software\SAP\SAPGUI Front\SAP Frontend Server\Security] “WarnOnConnection” (REG_DWORD) [Default: ”1”] {0 = inactive; 1 = active }
Please find attached code for updating RegEditior to enable Client Side Scripting