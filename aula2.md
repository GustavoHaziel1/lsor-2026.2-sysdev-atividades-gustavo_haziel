1. Criar o grupo financeiro
sudo groupadd financeiro

2. Associar cicrano e beltrano ao grupo
sudo usermod -aG financeiro cicrano
sudo usermod -aG financeiro beltrano

pra validar:
grep financeiro /etc/group


3. Criar a pasta compartilhada
sudo mkdir -p /srv/financeiro

4. Definir dono, grupo e permissões
sudo chown administrador /srv/financeiro
sudo chgrp financeiro /srv/financeiro
sudo chmod 770 /srv/financeiro
ls -ld /srv/financeiro

Dono administrador: rwx (controle total).
Grupo financeiro: rwx (leitura e escrita).
Outros: ---. 

5. Testes no terminal

Teste A: cicrano (membro de financeiro) deve conseguir

su - cicrano
cd /srv/financeiro
echo "Relatorio financeiro - Outubro" > relatorio.txt
echo "Revisado por Cicrano" >> relatorio.txt
cat relatorio.txt
ls -l
exit

Teste B: fulano (só em devs) deve ser negado

su - fulano
cd /srv/financeiro
ls -l /srv/financeiro
exit

Teste C: novato (usuário externo) deve ser negado

su - novato
cd /srv/financeiro
ls -l /srv/financeiro
exit