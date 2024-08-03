# Portas AD

### Abertas no WS2019
53  
88  
123  
135  
137  
389  
445  
464  
636  
3268  
3269  
49152-65535

### Link Microsoft
Porta(s) do Cliente		| Porta do Servidor	| Serviço
:---					| :---				| :---
49152-65535/UDP			| 123/UDP			| W32Time
49152-65535/TCP			| 135/TCP			| Mapeador de Ponto de Extremidade RPC
49152-65535/TCP			| 464/TCP/UDP		| Alteração de senha do Kerberos
49152-65535/TCP			| 49152-65535/TCP	| RPC para LSA, SAM, NetLogon (*)
49152-65535/TCP/UDP		| 389/TCP/UDP		| LDAP
49152-65535/TCP			| 636/TCP			| LDAP SSL
49152-65535/TCP			| 3268/TCP			| LDAP GC
49152-65535/TCP			| 3269/TCP			| LDAP GC SSL
53, 49152-65535/TCP/UDP	| 53/TCP/UDP		| DNS
49152-65535/TCP			| 49152-65535/TCP	| FRS RPC (*)
49152-65535/TCP/UDP		| 88/TCP/UDP		| Kerberos
49152-65535/TCP/UDP		| 445/TCP			| SMB (**)
49152-65535/TCP			| 49152-65535/TCP	| DFSR RPC (*)

### Link Wikipedia
[Wikipedia](https://pt.wikipedia.org/wiki/Lista_de_portas_dos_protocolos_TCP_e_UDP)

| Porta(s) do Cliente	| Porta do Servidor	| Serviço
| :---					| :---				| :---
|						| 137/TCP/UDP		| Netbios
|						| 593/TCP/UDP		| HTTP RPC Ep Map
|						| 5357/TCP			| WS-Discovery
|						| 5985/TCP			| Chamadas do PowerShell
|						| 9389/TCP			| Active Directory Web Services
|						| 47001/TCP			| Serviço de gerenciamento remoto do sistema/Windows
