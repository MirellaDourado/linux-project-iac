# Criação de Estrutura

## Para a utilização deste arquivo:

*O arquivo possui nomes, grupos e diretórios fictícios que foram pedidos pelo projeto, há a necessidade de muda-los caso haja a execução para fins próprios*

  1. Baixar o diretório
  2. Abrir o arquivo para modificação no terminal com o comando: 'nano iac.sh'
  3. Após a modificação salvar com 'cntrl o' depois 'enter'
  4. Com o usuário root, modifique para que o arquivo possa ser executado com o comando: 'chmod +x iac.sh'
  5. Utilize o comando para sua execução: ./iac.sh
  6. Para verificar se tudo ocorreu como esperado pode-se utilizar:
      - para checar os usuários: 'cat /etc/passwd'
      - para checar os grupos: 'cat /etc/group'
      - para checar as permissões e os diretórios: 'cd /' e 'ls -l'

## Modificação do arquivo

Para modificar os diretórios basta mudar os nomes após a '/' (barra), na seção: **echo "Criando diretórios..."**

ANTES:

    mkdir /publico

MODIFICADO:

    mkdir /todos

Para modificar os grupos basta mudar os nomes dos grupos após o 'groupadd', na seção: **echo "Criando grupos..."**

ANTES:

    groupadd GRP_ADM

MODIFICADO:

    groupadd SETORIAL

Para modificar os usuários basta mudar os nomes após 'useradd' e para mudar a senha muda a parte 'Senha123', na seção: **echo "Criando usuários e os adicionando aos grupos..."**

*As partes -G dizem respeito ao grupo que o usuário pertence, basta mudá-lo*

ANTES:

    useradd carlos -m -s /bin/bash -p $(openssl passwd -crypt Senha123) -G GRP_ADM

MODIFICADO:

    useradd antonio -m -s /bin/bash -p $(openssl passwd -crypt 321Senha) -G SETORIAL
