# ambiente-Docker-com-PHP-Apache-PostgreSQL-e-pgAdmin

Aqui vamos criar um ambiente Docker completo com PHP, Apache, PostgreSQL e pgAdmin. Esses componentes são fundamentais para o desenvolvimento web e administração de bancos de dados.

Vamos começar definindo os arquivos necessários: docker-compose.yml, Dockerfile, um arquivo de configuração do Apache e um arquivo index.php para testar a conexão com o banco de dados PostgreSQL.

## Crie o arquivo index para testar a conexão
Crie um diretório src na raiz e dentro dele crie o arquivo (index.php)

## Agora que temos todos os arquivos necessários, vamos explicar o que cada um faz:

    docker-compose.yml: Este arquivo define os serviços que serão executados no ambiente Docker. Ele especifica três serviços: PHP com Apache, PostgreSQL e pgAdmin. Cada serviço possui configurações específicas, incluindo portas mapeadas para acesso externo e variáveis de ambiente para configuração.

    Dockerfile: Este arquivo é usado para construir a imagem do contêiner PHP com Apache. Ele instala as extensões necessárias do PHP para trabalhar com o PostgreSQL, copia o arquivo de configuração do Apache e ativa o mod_rewrite.

    apache-config.conf: Este é o arquivo de configuração do Apache que define as configurações do servidor. Ele permite a sobreposição de configurações em diretórios específicos e habilita a reescrita de URL.

    index.php: Este script PHP tenta se conectar ao PostgreSQL usando as credenciais fornecidas no arquivo docker-compose.yml. Se a conexão for bem-sucedida, ele exibirá a mensagem "Conexão bem-sucedida via PostgreSQL!". Se ocorrer algum erro durante a conexão, ele exibirá a mensagem de erro correspondente.

Para iniciar o ambiente Docker, basta navegar até o diretório onde esses arquivos estão localizados e executar o comando (docker compose up -d). Isso irá construir as imagens, criar os contêineres e iniciar os serviços.

Após iniciar os contêineres, você poderá acessar seu aplicativo PHP em (http://localhost) e o pgAdmin em (http://localhost:8080). Certifique-se de que nenhum outro serviço esteja utilizando as portas especificadas para evitar conflitos.
