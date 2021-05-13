## Configurações DHCPv4

**Excluir endereços específicos**

Exemplo:

(config)#ip dhcp excluded-address 192.168.10.1 192.168.10.9

```
(config)#ip dhcp excluded-address [intervalo-entre-os-endereços-ip]
```

**Configuração de um pool DHCPv4**

Exemplo: 

(config)#ip dhcp pool LAN-POOL-1

(dhcp-config)#

```
(config)#ip dhcp pool [pool-name]
```

**Definir o pool de endereços**

Exemplo: 

(dhcp-config)#network 192.168.10.0 255.255.255.0

```
(dhcp-config)#network [network-number]
```

**Definir o roteador ou gateway padrão**

Exemplo: 

(dhcp-config)#default-router 192.168.10.1

```
(dhcp-config)#default-router [endereço-ip]
```

**Definir um servidor DNS**

Exemplo:

(dhcp-config)#dns-server 192.168.11.5

```
(dhcp-config)#dns-server [endereço-ip-do-servidor-de-dns]
```

**Definir o nome de domímio**

Exemplo:

(dhcp-config)#domain-name example.com

```
(dhcp-config)#domain-name [nome-de-domínio]
```

**Definir a duração do aluguel do DHCP**

```
(dhcp-config)#lease [dias-horas-minutos-infinite]
```

**Definir o servidor NetBIOS WINS**

```
(dhcp-config)#netbios-name [endereço-ip-do-servidor-de-netbios]
```

**Desativar / Reativar o DHCPv4**

OBS: O serviço DHCPv4 fica ativado por padrão.

```
(config)#no service dhcp (desativar)
ou
(config)#service DHCP (reativar)
```

**Solicitação de um servidor DHCPv4 que esteja em uma outra sub-rede / RETRANSMISSÃO**

OBS: Esse comando será atrelado na interface do roteador que receberá o broadcast de solicitação de endereço IPv4 de um determinado host

Exemplo:

(config)#int g0/1

(config-if)#ip helper-address 192.168.11.6

```
(config-if)#ip helper-address [endereço-ip-do-servidor-de-DHCPv4-em-uma-outra-subrede]
```

**Configuração de um roteador como cliente DHCP**

OBS: Essa configuração será atrelada na interface de um roteador SOHO conectada à um roteador ISP

```
(config-if)#ip address dhcp
```

**Exibir os comandos DHCPv4 configurados no Router**

```
#show running-config | section dhcp
```

**Exibir uma lista de todos os endereços IPv4 para associações de endereço MAC que foram fornecidas pelo serviço DHCPv4**

```
#show ip dhcp binding
```

**Exibir informações sobre a quantidade de mensagens DHCPv4 que foram enviadas e recebidas**

```
#show ip dhcp server statistics
```

**Exibir todos os conflitos de endereço gravados pelo servidor DHCPv4**

```
#show ip dhcp conflict
```

**Reportar eventos de servidor, como atribuições de endereço e atualizações de banco de dados**

```
#debug ip dhcp server events
```
