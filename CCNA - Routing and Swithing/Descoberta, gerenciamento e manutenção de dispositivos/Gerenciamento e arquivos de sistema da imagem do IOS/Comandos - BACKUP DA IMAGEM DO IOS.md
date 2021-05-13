## BACKUP DA IMAGEM DO IOS

**Teste de conectividade no servidor TFTP**

```
#ping [endereço-ip-do-servidor]
```

**Verifique se o servidor TFTP tem espaço suficiente em disco para acomodar a imagem do software IOS Cisco**

```
#show flash0
```

**Copiar a configuração para o servidor TFTP**

```
#copy flash0: tftp:
[nome-do-arquivo]
[endereço-ip-do-servidor]
```

**Copiar o arquivo de imagem do IOS do servidor TFTP para o dispositivo**

```
#copy tftp: flash0:
[nome-do-arquivo]
[endereço-ip-do-servidor]
```

**Atualizar para a imagem do IOS copiado após ter salvo essa imagem na memória flash**

```
(config)#no boot system
(config)#boot system flash: [nome-da-imagem]
#copy running-config startup-config
#reload
```

**Verificar a imagem carregada**

```
#sh version
```
