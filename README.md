# Pojeto Integrador III
# Pipeline de entrega continua de infraestrutura na AWS.
Repositório da disciplina projeto integrador III.

O projeto consiste na criação de um pipeline de entrega continua de infraestrutra na aws.

- Neste repositorio conterá os arquivos e procedimentos necessários para cria um pipeline de entrega continua de uma aplicação e sua infraestrutura utilizando as tecnologias Github, Jenkins, Terraform, Ansible, Shell Script, Docker, Docker-compose e Amazon Web Services.

- Listagem de diretórios e arquivos:
		
	- Ansible - Arquivos e procedimentos para a gestão de configuração do ambiente.
	- Docker - Arquivos e procedimentos para deploy da aplicação com docker e docker-compose.
	- Terraform - Arquivos e procedimentos para deploy da infraestrutura na AWS (infra as a code).
  	- Jenkinsfile - Arquivo que contém a definição do pipeline Jenkins.
	- teste.sh - Arquivo em Shell Script reponsável por realizar testes no ambiente e na aplicação.

- Procedimeto para configuração do ambiente
	
	- Instale um servidor jenkins - mais informações sobre a instalação (https://jenkins.io/doc/).
	- Instale o terraform na maquina jenkins - mais informações sobre a instalação (https://www.terraform.io/docs/index.html).
	- Instale o ansible na máquina jenkins - mais informações sobre a instalação (https://www.ansible.com/).
	- Tenha uma conta na AWS - mais informações de como criar uma conta (https://aws.amazon.com/).
	
# Criando ACCESS_KEY na AWS
- Para que o jenkins possa acessar o recursos da AWS é necessária criar um access_key.
Siga o passo a passo da documentação oficial - https://docs.aws.amazon.com/pt_br/IAM/latest/UserGuide/id_credentials_access-keys.html

# Configurando o Jenkins
- Após a instalação do servidor jenkins será necessários fazer alguns ajustes. Para que o jenkins acesse a aws é necessário salvar o access_key e o secret_key em váriavel e depois exportar-la para todo sistema operacional do servidor jenkins.
- Faça acesso ssh a maquina do jenkins e exporte a seguintes variaveis:
		
	- export aws_acces_key=my_acces_key
	- export aws_region=my_region
	- export aws_secret_key=my_secret_key
		
- Instale os seguintes plugins no jenkins
	- Amazon web services sdk
	- Ansible plugin
	- Blue ocean (visualização do pipeline)
	- Git plugin
	- Terraform plugin





Executando os procedimentos acima,será criado uma instancia EC2 na AWS.

Para acessar a aplicação que foi utilizada para teste:
	
	Acesse o endereço http://endereço_publico_da_instancia_ec2:8080 (este app executa um arquivo index.php que conecta ao banco, insere dados e exibe os dados no browser).
	Usando o MySQL Workbench para acessar o banco:
		IP: IP_PUBLICO_DA_EC2
		user: docker
		senha: docker
		porta: 3306


# Integrantes:
	
	Anderson dos Santos Farias
	- Linkedin: https://www.linkedin.com/in/andersonfariass/
	Elvis de Jesus Gois
	Jodemi Cruz Santos
	- Linkedin: https://www.linkedin.com/in/jodemi-cruz-santos-67b97431/	
