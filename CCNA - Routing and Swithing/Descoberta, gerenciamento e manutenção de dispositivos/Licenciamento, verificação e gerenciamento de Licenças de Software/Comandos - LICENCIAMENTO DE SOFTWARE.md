## LICENCIAMENTO DE SOFTWARE

**Exibir informações adicionais sobre licenças de software IOS Cisco**

```
#sh license
```

**Exibir as licenças do pacote de tecnologia e as licenças de recursos suportadas**

```
#show license feature
```

**Exibição do UDI**

```
#sh license udi
``` 

**instalar um arquivo de licença**

```
#license install [stored-location-url]
```

**Reinicialize o dispositivo**

```
#reload
```

**Aceitar o Contrato de Usuário Final da Licença (EULA)**

```
(config)#license accept end user agreement
```

**Instalar o pacote de tecnologia de dados da avaliação**

```
(config)#license boot module [module-name] technology-package [package-name]
```

**Backup de uma cópia das licenças em um dispositivo**

```
#license save [file-sys:lic-location]
```

**Verificar se as licenças foram salvas**

```
#sh [file-sys:]
```

**Desativar o pacote de tecnologia**

OBS: recarregue o roteador usando o comando reload. Um recarregamento é exigido para tornar o pacote de software inativo.

```
(config)#license boot module [module-name] technology-package [package-name] disable
```

**Remover a licença**

OBS: apague o comando license boot module usado para desativar a licença ativa

```
#license clear [feature-name]
```