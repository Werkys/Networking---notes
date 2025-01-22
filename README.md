# Networking---notes
## Přístupové metody
> Console <br>

připojení přes consolový kabel. Možnost připojit se bez připojení k internetu.

> SSH (Secure Shell) <br>

Protokol SSH vytváří šifrované spojení mezi dvěma uzly, serverem a klientem.

> Telnet <br>

Telnet je podobný SSH ale není zašifrovaný, tudíž je nebezpečný a měl by se používat jenom v testovacím prostředí.


## Základní příkazy
> Switch> <br>

prostředí jen pro view
> Switch# 
prostředí pro úpravy <br>

          Switch> enable <br>
          Switch# 

          přenese nás z view do úprav <br>

                  Switch# disable <br>
                  Switch>

 A jsme zpět ve view <br>

> Switch(config)# pro konfiguraci zařízení <br>

          Switch# configure terminal <br>
          Switch(config)#

> Switch(config-line)# pro konfigurace console, SSH, Telnetu nebo AUX přístupu <br>

          Switch(config)# line console 0 <br>
          Switch(config-line)#

> Switch(config-if)# pro konfiguraci rozhraní portů nebo routerů <br>

          Switch(config)# interface FastEthernet 0/1 <br>
          Switch(config-if)# <br>

          (FastEthernet 0/1 je název portu)

>End vrátíme se zpět do prostředí úprav <br>

          Switch(config-if)# <br>
          Switch#


>Exit vrátíme se o krok zpět <br>

         Switch(config-if)# <br>
         Switch(config)#
          




 

 




