## PAT - Pool de Endereços

**Definir um pool de endereços globais a serem usados para conversão de sobrecarga**

OBS: Os endereços são definidos pela indicação do endereço IPv4 inicial e endereço IPv4 final do pool.

Exemplo: 

(config)#ip nat pool NAT-POOL2 209.165.200.226 209.165.200.240 netmask 255.255.255.224

```
(config)#ip nat pool [name] [intervalo-de-IPs] netmask [máscara]
```

**Configurar uma ACL padrão para permitir os endereços que devem ser convertidos**

Exemplo: 

(config)#access-list 1 permit 192.168.0.0 0.0.255.255

```
(config)#access-list [1-99] [deny or permit] [endereço-ip] [wildcard]
```

**Estabelecer a conversão de sobrecarga, especificando a lista de acesso e o pool**

Exemplo: 

(config)#ip nat inside source list 1 pool NAT-POOL2 overload

```
(config)#ip nat inside source list [número-da-acl] pool [name] overload
```

**Marcar a interface conectada internamente**

```
(config-if)ip nat inside
```

**Marcar a interface conectada externamente**

```
(config-if)ip nat outside
```

**Eliminar as estatísticas e as entradas**

```
#clear ip nat statistics
#clear ip nat translation *
```

**Exibir as conversões ativas de NAT**

```
#show ip nat translations
```

**Exibir informações sobre o número total de conversões ativas**

```
#show ip nat statistics
```

## PAT - Endereço único

**Configurar uma ACL padrão para permitir os endereços que devem ser convertidos**

Exemplo: 

(config)#access-list 1 permit 192.168.0.0 0.0.255.255

```
(config)#access-list [1-99] [deny or permit] [endereço-ip] [wildcard]
```

**Estabelecer a conversão dinâmica de origem, especificando as opções de ACL, interface de saída e sobrecarga**

Exemplo:

(config)#ip nat inside source list 1 interface serial 0/1/0 overload

```
(config)#ip nat inside source list [1-99] interface [id-da-interface] overload
```

**Marcar a interface conectada internamente**

```
(config-if)ip nat inside
```

**Marcar a interface conectada externamente**

```
(config-if)ip nat outside
```

**Eliminar as estatísticas e as entradas**

```
#clear ip nat statistics
#clear ip nat translation *
```

**Exibir as conversões ativas de NAT**

```
#show ip nat translations
```

**Exibir informações sobre o número total de conversões ativas**

```
#show ip nat statistics
```

**Verificar a operação do recurso NAT, exibindo informações sobre cada pacote que está sendo convertido pelo roteador**

```
#debug ip nat
#debug ip nat detailed 
```