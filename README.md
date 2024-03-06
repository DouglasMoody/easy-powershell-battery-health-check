# easy-powershell-battery-health-check
Powershell command to report usable remaining battery life

Simply press Windows Key + R > type powershell > press enter > Paste the next few lines in and press enter.


$DesignedCapacity = (Get-WmiObject -Class “BatteryStaticData” -Namespace “ROOT\WMI”).DesignedCapacity
$FullChargedCapacity = (Get-WmiObject -Class “BatteryFullChargedCapacity” -Namespace “ROOT\WMI”).FullChargedCapacity
Write-Host “Designed Capacity” $DesignedCapacity
Write-Host “Full Charged Capacity” $FullChargedCapacity
Write-Host “Battery Health:”(100*$FullChargedCapacity/$DesignedCapacity)“%”


##Taken from https://community.spiceworks.com/t/powershell-full-battery-charge-and-design-capacity/1011212
