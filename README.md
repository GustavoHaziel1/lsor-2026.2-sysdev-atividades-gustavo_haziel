# Prática 03: Interfaces e Endereçamento de Rede

## 1. Identificação
- Nome completo: Gustavo Haziel Almeida Lins de Carvalho Silva
- Matrícula: 2024335075
- Turma: 913A
- Data: 26/10/2026
- Título: Interfaces e Endereçamento de Rede

## 2. Objetivo
Inspecionar interfaces e rotas de uma VM Ubuntu Server 26.04 LTS, testar a
conectividade em camadas com ping e traceroute e comparar os modos NAT e
Placa em Ponte (Bridge) no VirtualBox.

## 3. Ambiente
- Hipervisor: VirtualBox
- VM: ubuntu_server, Ubuntu Server 26.04 LTS, 768 MB RAM, 1 CPU, 32 GB de disco
- Modo de rede 1: NAT
- Modo de rede 2: Bridge

## 4. Procedimento
1. ip addr show, ip link, ip route, netplan status
2. ping -c 4 em 127.0.0.1, IP da VM, 10.0.2.2, 8.8.8.8 e google.com
3. sudo apt update; sudo apt install -y traceroute; traceroute 8.8.8.8
4. Troca para Bridge e repetição de ip addr show, ip route e ping
5. ipconfig /all no host Windows

## 5. Testes


| | NAT | Bridge |
|---|---|---|
| IP da VM | 10.0.2.15 |
| Gateway | 10.0.2.2 |
| Host acessa a VM? | Não |

## 6. Problemas e Soluções
nenhum problema encontrado

## 7. Conclusão
Foram validadas as camadas de rede com ping e traceroute. No NAT o host não
alcança a VM porque ela fica em rede privada; no Bridge ela entra na rede do
laboratório e fica acessível.