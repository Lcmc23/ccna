## NTP

**Definir o horário de maneira manual**

Exemplo: 

#clock set 20:36:00 dec 11 2015

```
#clock set [hh:mm:ss] {mmm (em-inglês | apenas as 3 primeiras letras)} [dd] [aaaa]
```

**Indicar o número de saltos de NTP com relação a uma fonte de tempo autoritativa**

```
(config)#ntp master [nível-de-stratum]
```

**Configurar NTP**

```
(config)#ntp server [endereço-ip]
```

**Atualizar o calendário periodicamente com a hora do NTP**

```
(config)#ntp update-calendar
```

**Definir o fuso do relógio**

Exemplo: Definir PDT (Horário do Pacífico, que é 8h mais tarde que o GMT)

(config)#clock timezone PST -8

```
(config)#clock timezone [fuso] [gmt]
```

**Definir para o horário verão recorrente**

```
(config)#clock summer-time PDT recurring
```

**Exibir a hora atual no relógio do software**

```
#show clock [detail]
```

**Exibir informações**

```
#show ntp associations
#show ntp status
```