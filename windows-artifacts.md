## Windows Registry

- Find Hostname and Domain : HKLM\SYSTEM\ControlSet001\Services\TcpIP\Parameters

- List shared folders : HKLM\SYSTEM\ControlSet001\Services\LanmanServer\Shares

- Startup executable : NTUSER.dat - Software\Micorsoft\Windows\CurrentVersion\Run

- RDP connection history : NTUSER.dat - TerminalServerClient

- Log file launch via GUI (Win Explorer) : NTUSER.dat - UserAssist

- Track user folder access on local machine, network shares, removeable devices: ShellBags

- Persistence: HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\SilentProcessExit : configure monitoring actions when a process terminates silently (exits without user interaction or crashes).

###  SYSTEM hive

- SYSTEM\Select\Current : Identify the CurrentControlSet

- SYSTEM\CurrentContro1Set\Control\Timezone\TimeZoneInformation : Identify the timezone

- SYSTEM\CurrentControlSet\Control\FileSystem : Is the last access timestamp for files on or off?

- SYSTEM\CurrentControlSet\Control\ComputerName\ComputerName : Identify the computer name

- SYSTEM\CurrentControlSet\Services\Tcpip\Parameters\Interfaces : Identify the network interfaces and their IP addresses

- SYSTEM\CurrentControlSet\Services\LanmanServer\Shares : Identify the shares of the system and their configuration

### SOFTWARE hive

- SOFTWARE\Microsoft\WindowsNT\CurrentVersion\NetworkList\Signatures\Unmanaged and SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Profiles : Identify network profile , then use wigle.net to locate the position

## Disk Artifacts

- Amcache.hve stores info about programs that have been run on the machine : C:\Windows\AppCompat\Programs

- ConsoleHost_history.txt logs PowerShell command history : C:\Users\username\AppData\Roaming\Microsoft\Windows\PowerShell\PSReadLine

- Jump Lists located at C:\Users\user\AppData\Roaming\Microsoft\Windows\Recent\AutomaticDestinations store artifacts for proof of file access, tracking deleted files,...

- The hash for files that was marked malicious by Windows Defender can be found at C:\ProgramData\Microsoft\Windows Defender\Support\
