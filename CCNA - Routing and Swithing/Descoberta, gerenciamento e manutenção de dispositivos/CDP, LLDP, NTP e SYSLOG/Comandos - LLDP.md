## LLDP

**Ativar o LLDP globalmente em um dispositivo de rede da Cisco**

OBS: para desativar o LLDP, insira o comando 'no lldp run'

```
(config)#lldp run 
```

**Transmissão e recebimento de pacotes LLDP**

```
(config-if)#lldp transmit
(config-if)#lldp receive
``` 

**Verificar LLDP**

```
#show lldp
```

**Detectar os vizinhos**

```
#show lldp neighbors [detail]
```