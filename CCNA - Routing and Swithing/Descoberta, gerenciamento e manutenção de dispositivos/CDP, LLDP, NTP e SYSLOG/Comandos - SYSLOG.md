## SYSLOG

**Forçar eventos registrados a exibirem a data e hora**

OBS: se você usar a palavra-chave 'datetime', o relógio do dispositivo de rede deverá ser definido manualmente ou por NTP

```
(config)#service timestamps log datetime
ou
(config)#service timestamps log datetime msec
```

**Armazenar as mensagens de log por padrão**

OBS: os comandos devem seguir essa ordem

```
(config)#logging console
(config)#logging buffered
```

**Exibir as configurações de serviço de logging padrão**

```
#sh logging
```

## Comandos do roteador e do switch para clientes de Syslog

OBS: São necessários três passos para que o roteador envie mensagens do sistema a um Servidor syslog, onde elas podem ser armazenadas, 
filtradas e analisadas:

**Configurar o nome de host do destino ou o endereço IPv4 do syslog (Passo 1)**

```
(config)#logging [endereço-ipv4-do-syslog]
ou
(config)#logging host [endereço-ipv4-do-host-de-syslog]
```

**Controlar as mensagens que serão enviadas ao Servidor syslog (Passo 2)**

```
(config)#logging trap [nível]
```

**Configurar a interface de origem (Passo 3)**

```
(config-if)#logging source-interface [id-da-interface]
```

**Filtrar as saídas de syslog**

Exemplo:

#show logging | include changed state to up
#show logging | begin Jun 12 22:35

```
#sh logging | [parâmetro]
```