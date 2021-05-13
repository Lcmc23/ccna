## NAT - DINÂMICO

**Definir um pool de endereços globais a serem usados para conversão**

OBS: Os endereços são definidos pela indicação do endereço IPv4 inicial e endereço IPv4 final do pool.

Exemplo: 

(config)#ip nat pool NAT-POOL1 209.165.200.226 209.165.200.240 netmask 255.255.255.224

```
(config)#ip nat pool [name] [primeiro-ip-da-rede] [ultimo-ip-da-rede] netmask [máscara]
```

**Configurar uma ACL padrão para permitir os endereços que devem ser convertidos**

Exemplo: 

(config)#access-list 1 permit 192.168.0.0 0.0.255.255

```
(config)#access-list [1-99] [deny or permit] [endereço-ip] [wildcard]
```

**Estabelecer a conversão dinâmica de origem, especificando a lista de acesso e o pool**

Exemplo: 

(config)#ip nat inside source list 1 pool NAT-POOL1

```
(config)#ip nat inside source list [número-da-acl] pool [name]
```

**Marcar a interface conectada internamente**

```
(config-if)ip nat inside
```

**Marcar a interface conectada externamente**

```
(config-if)ip nat outside
```

**Remover conversões de NAT**

```
#clear ip nat translations *
```

**Exibir as conversões ativas de NAT**

```
#show ip nat translations
```

**Exibir informações sobre o número total de conversões ativas**

```
#show ip nat statistics
```

**Eliminar as estatísticas e as entradas**

```
#clear ip nat statistics
#clear ip nat translation *
```

**Verificar a operação do recurso NAT, exibindo informações sobre cada pacote que está sendo convertido pelo roteador**

```
#debug ip nat
#debug ip nat detailed 
```

