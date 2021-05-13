## Configurações DHCPv6

**Ativar o roteamento IPv6**

```
(config)# ipv6 unicast-routing
```

**Configurar um pool de DHCPv6**

Exemplo: 

(config)#ipv6 dhcp pool IPV6-STATELESS

```
(config)#ipv6 dhcp pool [pool-name]
(config-dhcpv6)#
```

**Configurar os parâmetros do pool**

Exemplo:

(config-dhcpv6)#address prefix 2001:db8:cafe:1::/64 lifetime infinite

(config-dhcpv6)#dns-server 2001:db8:cafe:1:aaaa:5

(config-dhcpv6)#domain-name example.com

```
(config-dhcpv6)#address prefix [endereço-ip-e-máscara] {[lifetime [valid-lifetime or preferred-lifetime | infinite]}
(config-dhcpv6)#dns-server [endereço-ip-do-servidor-de-dns]
(config-dhcpv6)#domain-name [nome-do-domínio]
```

**Configurar a interface do DHCPv6**

```
(config)#int [id-da-interface]
(config-if)#ipv6 add [endereço-ip]
(config-if)#ipv6 dhcp server [pool-name]
(config-if)#[nesta-etapa-devemos-especificar-o-modo-de-operação-que-o-roteador-irá-trabalhar]
```

**Restaurar as flag M e O para seus valores iniciais de 0 - SLAAC padrão**

OBS: As mensagens de RA são configuradas em uma interface individual de um roteador.

```
(config-if)# no ipv6 nd managed-config-flag [flag-M-restaurada]
(config-if)# no ipv6 nd other-config-flag [flag-O-restaurada]
```

**Utilizar DHCPv6 Stateless**

OBS: Flag M = 0; Flag O = 1

```
(config-if)# ipv6 nd other-config-flag
```

**Utilizar DHCPv6 Stateful**

OBS: Flag M = 1; Flag O = não está envolvida

```
(config-if)#ipv6 nd managed-config-flag
```

**Configuração de um roteador como cliente de SLAAC ou DHCPv6 stateless**

OBS: Este não é um cenário típico e é usado somente para fins de demonstração.

```
(config)#int [id-da-interface]
(config-if)#ipv6 enable
(config-if)#ipv6 add autoconfig
```

**Configuração de um roteador como cliente de DHCPv6 Stateful**

OBS: Essa configuração será atrelada na interface de um roteador SOHO conectada à um roteador ISP

```
(config)#int [id-da-interface]
(config-if)#ipv6 address dhcp
```

**Configuração de um roteador como um agente de retransmissão de DHCPv6**

OBS: Esse comando é configurado na interface voltada para o cliente usando o endereço do servidor DHCPv6 como destino.

```
(config)#int [id-da-interface]
(config-if)#ipv6 dhcp relay destination [endereço-ip-do-servidor-de-IPv6]
```

**Verificação dos servidores DHCPv6 stateful**

```
#show ipv6 dhcp pool - verificar as configurações
#show ipv6 dhcp binding - verificar as vinculações
```

**Verificação do cliente DHCPv6 stateful**

```
#show ipv6 int [id-da-interface] - verificar as configurações
```

**Exibe todos os conflitos de endereço registrados por servidores DHCPv6 stateful**

```
#show ipv6 dhcp conflict
```

**Verificar a recepção e a transmissão de mensagens DHCPv6**

```
#debug ipv6 dhcp detail
```