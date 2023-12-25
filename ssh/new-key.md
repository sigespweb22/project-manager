# Este documento instrui sobre a criação de uma nova chave SSH para autenticação e acesso ao GitHub e GitLab

## Gerar uma nova chave SSH
1. Abra o terminal
2. ssh-keygen -t ed25519 -C "your_email@example.com"
Siga os passos da etapa 2 e pronto, será gerado duas chaves, uma pública (.pub) e outra privada.
A chave privada você adiciona ao ssh-agent localmente para não ter que ficar informando a palavra passe toda hora, e a chave pública você adicionar nas configurações do gitlab ou github 

## Adicionar sua chave SSH ao ssh-agent
1. eval "$(ssh-agent -s)"
2. ssh-add ~/.ssh/"nome da sua chave privada, se seguir os passos acima sem mudar o nome, será id_ed25519"
3. Copie e adicione a chave pública SSH gerada à sua conta em GitHub

## Testar conexão SSH com github
ssh -T git@github.com
