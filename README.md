# fix_that_linux_mic
Arruma o tal bug do linux do microfone do headset que não é reconhecido.

Primeiro baixe o alsa-tools-gui:
```sh
sudo apt-get update
sudo apt-get install alsa-tools-gui
```
Você precisa ter privilégios de administrador para realizar a próxima ação.
Depois edite o arquivo de configuração do pulse da forma que conseguir, eu vou usar o vscode pra isso:
```sh
sudo code --no-sandbox /etc/pulse/client.conf
```
Adicione no arquivo as configurações abaixo:
```txt
autospawn = no
daemon-binary = /bin/true 
```
Reinicie o computador e agora você pode desligar e ligar o pulse audio sem ele .
Depois de reiniciado você fará o seguinte comando:

## Caso necessite volte aqui.

```sh
# Para eu que estou usando linux mint 21.1
systemctl --user stop pulseaudio.socket pulseaudio.service
# Para alguns será assim:
pulseaudio --kill
```

Agora vamos procurar pelo HDAJackReTask.
###### Inserir imagem aqui
Agora vamos ativar para que os pinos não conectados apareçam.
Agora vamos procurar o pino correto para ativar.
Depois basta aplicar.

Agora basta realizar o comando abaixo:

```sh
# Para eu que estou usando linux mint 21.1
systemctl --user start pulseaudio.socket pulseaudio.service

# Alguns funcionará assim:
pulseaudio --start
```

Agora teste e veja se o pino funcionou, caso não funcione, tente outro pino que tenha o microfone. Repetindo o processo daqui. (Inserir link)
