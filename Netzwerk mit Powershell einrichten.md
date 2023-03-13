## Computer umbenennen
    Rename-Computer -ComputerName C1 -NewName C2 -DomainCredential dwp\admin -restart

## lokaler Benutzer umbennen
    Rename-LocalUser -Name "Power" -NewName "Austin" -confirm

## anzeigen lassen
    Get

## ping auf bestimmte Ip im Netzwerk
    ping 172.16.0.10

## Ip‘s im Netzwerk anzeigen
    arp -a

## IP einlenden
    IPConfig

## ausloggen einloggen
    LogOff oder LogOn

## gibt Liste der Netzwerk Adadapter aus
    Get-NetAdapter

## Gateway entfernen
    Remove-Netroute 0.0.0/0 -nexthop 172.168.0.1

## IP Adresse vergeben
    New-NetIPAddress 172.16.0.100 prefixlength 16 -Defaultgateway 172.16.0.1 -InterfaceAlias Ethernet oder LAN1

## installiert notwendige Programme für Active Directory oder DNS
Install-windowsfeature AD-Domain-Services


Rename-Netadapter -InterfaceAlias Ethernet -Newname LAN1 
(umbenennen Netztwerk)

Remove-NetIPadress 172.16.0.0 -InterfaceAlias LAN2
(IP Adresse entfernen)

Set-DnsClientServerAddress -InterfaceAlias LAN1 -ServerAddresses 192.168.1.10
(DNS Client setzen)

Netstat -r 
(Routentabelle)

Get-NetRoute -AddressFamily ipv4 
(IP Familie anzeigen)

New-NetRoute 172.16.0.0/16 -nexthop 192.168.1.254 Ethernet 
(Route zum ander Server herstellen Remove würde die Rote entfernen)

Install-ADDSDomainController -DomainName r1.kurs.iad
Install-ADDSDomainController -DomainName r1.kurs.iad -SafeModeAdministratorPassword ( Read-Host -AsSecureString -Prompt "Bitte das Kennwort" ) -Force
(Domain Controller installieren und oder Passwort setzen)

Install-ADDSDomainController -DomainName r1.kurs.iad -SafeModeAdministratorPassword ( Read-Host -AsSecureString -Prompt "Bitte das Kennwort" ) -Force -Credential $cred

Get-WindowsFeature | ? Name -Like Ad-Domain*
(überprüfen ob die Domain installiert ist)

New-NetFirewallRule -DisplayName "Allow Ping" -Direction Inbound -Protocol ICMPv4 -IcmpType 8 -Action Allow
(Ping erlauben)

Set-NetIPInterface -Forwarding Enabled -InterfaceAlias LAN2
(Forw
arding)

Get-Netadapter | select name,mediaconnectionstate

rename-Netadapter Ethernet -Newname Lan2

rename-Netadapter "Ethernet2" -Newname Lan3



