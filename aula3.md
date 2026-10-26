1. Inspeção das interfaces e rotas

ip addr show
ip link
ip route
netplan status

Resultado típico em NAT:

Item	Valor típico
Interface	enp0s3
IP/prefixo	10.0.2.15/24 
MAC	08:00:27:54:77:12
Gateway padrão	10.0.2.2 
DNS	10.0.2.3 
Loopback	lo, 127.0.0.1/8

2. Ping em camadas

ping -c 4 127.0.0.1
ping -c 4 10.0.2.15     
ping -c 4 10.0.2.2
ping -c 4 8.8.8.8
ping -c 4 google.com

3. Rastreamento de rotas
sudo apt update
sudo apt install -y traceroute
traceroute 8.8.8.8

4. Modo Placa em Ponte (Bridge)
sudo poweroff.
ip addr show
ip route
ping -c 4 8.8.8.8

5. Comparação com o host Windows
PS C:\Users\Aluno> ipconfig /all