## CDP

**Verificar o status do CDP e exibir informações sobre ele**

```
#show cdp
```

**Ativar globalmente o CDP em todas as interfaces compatíveis do dispositivo**

OBS: para desativa-lo, basta colocar o parâmetro "no" antes do comando

```
(config)#cdp run
```

**Desativar o CDP em uma interface específica (como a interface voltada para um ISP por exemplo)**

OBS: para ativar, basta retirar o "no"

```
(config-if)#no cdp enable
``` 

**Verificar o status do CDP e exibir uma lista de vizinhos**

```
#show cdp neighbors [detail]
```

**Exibir as interfaces ativadas para CDP em um dispositivo**

```
#show cdp interface
```

