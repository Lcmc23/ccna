## Encaminhamento de portas

**Estabelecer a conversão estática entre um endereço local interno e uma porta local para um endereço global interno e a porta global**

Exemplo: 

(config)#ip nat inside source static tcp 192.168.10.254 80 209.165.200.225 8080

```
(config)#ip nat inside source [static (tcp or udp)] [ip-local-interno] [porta-local] [ip-global-interno] [porta-global]
```

**Identificar a interface interna de NAT**

```
(config)#int [id-da-interface-interna]
(config-if)#ip nat inside
```

**Identificar a interface externa de NAT**

```
(config)#int [id-da-interface-externa]
(config-if)#ip nat outside
```

**Verificar o encaminhamento de portas**

```
#sh ip nat translations