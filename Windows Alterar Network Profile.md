```powershell-interactive
get-netConnectionProfile

set-netConnectionProfile -InterfaceIndex 12 -NetworkCategory Private

set-netConnectionProfile -InterfaceIndex 22 -NetworkCategory Private

get-netConnectionProfile
