## NAT - ESTÁTICO

**Estabelecer a tradução estática entre um endereço local interno e um endereço global interno**

OBS: Conversões de NAT estático são usadas geralmente quando os clientes da rede externa (Internet) precisam acessar servidores da rede interna.

Exemplo:

(config)#ip nat inside source static 192.168.11.99 209.165.201.5

```
(config)#ip nat inside source static [ip-local] [ip-global]
```

**Marcar a interface conectada internamente**

```
(config-if)ip nat inside
```

**Marcar a interface conectada externamente**

```
(config-if)ip nat outside
```

**Exibir as conversões ativas de NAT**

```
#show ip nat translations
```

**Exibir informações sobre o número total de conversões ativas**

OBS: Para verificar se a conversão de NAT está funcionando, é melhor limpar as estatísticas de algumas conversões do passado usando o comando clear ip nat statistics e clear ip nat translation antes de testar.

```
#show ip nat statistics
```

**Verificar a operação do recurso NAT, exibindo informações sobre cada pacote que está sendo convertido pelo roteador**

```
#debug ip nat
#debug ip nat detailed 
```
