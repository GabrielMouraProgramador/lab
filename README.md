## Recuperando a senha inicial do Jenkins

Para obter a chave secreta (senha inicial) do Jenkins, execute o seguinte comando:

`bash`
sudo cat jenkins_home/secrets/initialAdminPassword

---

# Jenkins Home Directory (`/var/jenkins_home`)

Este diretório é onde o Jenkins armazena todos os seus dados essenciais e configurações. Ele contém informações cruciais sobre os jobs, plugins, histórico de builds, credenciais e mais. No caso deste repositório, ele é montado em um volume Docker para persistência de dados.

### O que é armazenado aqui?

- **Jobs**: Definições e configurações de todos os jobs configurados no Jenkins.
- **Builds**: Histórico dos builds realizados pelos jobs.
- **Plugins**: Todos os plugins instalados no Jenkins, incluindo suas configurações.
- **Configurações do Jenkins**: Arquivos de configuração gerais do Jenkins, como o `config.xml`.
- **Credenciais**: Informações sensíveis e credenciais usadas nos jobs.

### Por que isso está em um volume?

Para garantir a persistência de dados do Jenkins mesmo quando o container Docker é recriado ou atualizado. Montando este diretório como um volume, os dados do Jenkins não são perdidos entre execuções, permitindo continuidade nos trabalhos e configurações.

### Importância da Persistência

Como o Jenkins é uma ferramenta de automação essencial, garantir que seus dados estejam sempre disponíveis e seguros é fundamental. Este volume permite que todas as informações sejam preservadas e restauradas conforme necessário, evitando retrabalho na configuração de jobs e plugins.
