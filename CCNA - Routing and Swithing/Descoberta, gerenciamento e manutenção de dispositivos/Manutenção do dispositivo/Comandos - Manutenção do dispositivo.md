## Manutenção do dispositivo 

**Listar todos os sistemas de arquivos disponíveis em um roteador e um switch Cisco**

```
#show file systems
```

**Listar os conteúdos da flash**

```
#dir
```

**Exibir o conteúdo da NVRAM**

```
#cd nvram:
#Pwd (verifica se estamos exibindo o diretório da NVRAM)
#dir
```

**Salvar a configuração atual ou a configuração inicial em um servidor TFTP**

OBS: deve-se configurar

- endereço IP do host onde o arquivo de configuração está armazenado;

- nome que será atribuído ao arquivo de configuração.

```
# copy running-config tftp 
ou 
#copy startup-config tftp
``` 

**Visualizar o conteúdo da unidade flash USB**

```
#dir usbflash0:
```

**Copiar o arquivo de configuração para a unidade flash USB**

OBS: A barra é opcional, mas indica o diretório raiz da unidade flash USB

dir - para ver o arquivo na unidade USB

more - para ver o conteúdo

```
#copy run usbflash0:/ 
```

**Restaurar as configurações com uma unidade USB flash**

OBS: Com o objetivo de copiar o arquivo de volta, será necessário editar o arquivo R1-Config da USB usando um editor de textos. Considere que 
o nome do arquivo é R1-Config.

```
#copy usbflash0/R1-Config running-config
```

**Recuperar a configuração inicial e alterar senhas**

```
Digitar a sequência de interrupção - Ctrl+Break (PuTTY)

rommon 1 > confreg 0x2142
rommon 2 > reset
```

**Após a conclusão do recarregamento do dispositivo**

```
#copy startup-config running-config
```

**Definir as senhas novamente**

```
(config)#enable secret [senha]
(config)#config-register 0x2102
(config)#end
#copy running-config startup-config
#reload
```


