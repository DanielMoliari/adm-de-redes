# Administração de Redes
## Dados
#### Proxmox:
Login
Senha
#### Root
Login
Senha
#### Usuário 
Login
Senha
#### IP
192.168.67.***
#### MAS
255.255.255.0
#### GW:
192.168.67.1
#### DNS:
8.8.8.8
#### Codes Emergency OTP
******
******
******
******
******
#### ClouDNS
Usuario
email
senha
## Comandos
#### Listar arquivos e diretórios
ls
ls -l
ls -la
ls -a
ls -al
ls -la --color
ls -lah --color
ls --help
#### Manual
man ls
#### Ver diretório atual:
pwd
#### Navegar diretórios:
cd
cd / (raiz do sistema)
cd ~ ou cd (home do usuario)
#### Limpar terminal:
clear
#### Criar arquivo:
touch arquivoteste
#### Criar diretório:
mkdir dirteste
mkdir -p (cria diretórios pai)
#### Copiar arquivo:
cp arquivo1 copia_doArq1
#### Movimentar arquivos/renomear:
mv arquivo1 novoNomeArq1
#### Apagar arquivo:
rm arquivoTeste
#### Apagar diretório:
rm dirteste -rf
#### 
Executar um comando em sub-bash:
... &

#### Pega a saida do primeiro comando e joga para o primeiro comando:
comando | comando

#### Executa um, depois o outro, independente do status do primeiro:
comando ; comando

#### Executa o segundo se o primeiro tiver sucesso:
comando && comando

#### Executa o segundo comando se o primeiro não tiver sucesso:
comando || comando

#### Executa o comando e joga dentro de arquivo:
comando > arquivo (altera)
comando >> arquivo (adiciona)
comando 2>> /dev/null (jogar no limbo)
#### Printar no terminal:
echo
#### Listar conteúdo de arquivo:
cat arquivo
cat -n arquivo (numera linha)
#### Listar histórico de comandos (Log):
history
history -c (limpa os logs)
#### Procurar arquivo:
find / | grep arquivo
#### Filtro:
grep a
grep ab
grep abc...
#### Logar tudo que o usuario faz:
tail -f /var/log/apache2/*.log
#### Editor de texto:
nano arquivo

## Passo a passo configuração:

ip a

nano /etc/networking/interfaces

auto ens18

iface ens18 inet static
TAB address ip
TAB netmask
TAB gateway
TAB dns-nameservers

reboot

ping uol.com.br

nano /etc/apt/sources.list


deb http://deb.debian.org/debian/ bookworm main contrib non-free non-free-firmware

deb http://security.debian.org/debian-security bookworm-security main contrib non-free non-free-firmware

deb http://deb.debian.org/debian/ bookworm-updates main contrib non-free non-free-firmware

deb http://deb.debian.org/debian/ bookworm-backports main contrib non-free non-free-firmware


apt update

apt full-upgrade

backup

apt install openssh-server

Terminal local:

ping 192.168.67.***

ssh root 192.168.67.***

Terminal maquina:
nano /etc/ssh/sshd_config
PermitRootLogin yes

systemctl restart sshd

apt install cockpit

nano /etc/cockpit/disallowed-users
comentar root

https://192.168.67.***:9090

apt install libpam-google-authenticator

google-authenticator -t

nano /etc/pam.d/cockpit
auth required pam_google_authenticator.so


