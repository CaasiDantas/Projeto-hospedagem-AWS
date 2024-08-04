# 💻 Implementação de Site WordPress na AWS 

### 🤔 1. Objetivo do projeto 
Este projeto teve como objetivo a criação de uma instância na Amazon Web Services (AWS) para hospedar um site. O site foi desenvolvido para explicar e apresentar o curso de Redes de Computadores que estamos cursando.

### ⌨ 2. Tecnologias Utilizadas
Amazon Web Services (AWS): Plataforma de nuvem usada para hospedar a instância.
Amazon EC2 (Elastic Compute Cloud): Serviço da AWS usado para criar a instância de servidor.
Amazon RDS (Relational Database Service): Serviço gerenciado de banco de dados usado para hospedar e gerenciar o banco de dados do site.

### ⚙ 3. Configuração da Instância na AWS
#### 3.1. Criação da Instância EC2
Acessar o Console da AWS: Primeiramente, acessamos o console da AWS utilizando nossas credenciais.
Navegar até o EC2: No painel da AWS, selecionamos o serviço EC2 para iniciar a criação de uma nova instância.
Escolha da AMI (Amazon Machine Image): Selecionamos uma imagem com o sistema operacional Ubuntu Server 20.04 LTS.
Configuração da Instância: Escolhemos uma instância do tipo t2.micro, que é elegível para o nível gratuito.

#### 3.2. Configuração de Segurança: Configuramos o grupo de segurança para permitir o tráfego nas seguintes portas:



<table>
 <tr>
  <td>   
   
   IPv4
   
 </td>

 <td>
  
   HTTP (Porta 80) e HTTPS (Porta 443)
   
  </td>
 </tr>
 
 <tr>
 <td>
  
   IPv6
   
  </td>

 

 <td>
  
   HTTP (Porta 80) e HTTPS (Porta 443)
   
  </td>
 </tr>


</table>



#### 3.3. Configuração do Amazon RDS
Criação do Banco de Dados RDS: No console da AWS, navegamos até o serviço Amazon RDS e criamos uma nova instância de banco de dados.
Escolha do Banco de Dados: Optamos pelo  banco de dados PSQL.
Configuração da Instância: Escolhemos uma instância db.t2.micro para o banco de dados, que é elegível para o nível gratuito.
Configuração de Segurança: Configuramos o grupo de segurança do RDS para permitir conexões apenas a partir da nossa instância EC2.
Comunicação entre EC2 e RDS: Adicionamos o grupo de segurança padrão (default) à instância EC2 para permitir que ela se comunique com o RDS, garantindo que o tráfego entre a EC2 e o banco de dados seja permitido.

Configuração de Acesso ao Banco de Dados:
Definimos um nome de usuário e senha para acessar o banco de dados.
Configuramos o endpoint do RDS na aplicação web para que o site possa se conectar ao banco de dados.

#### 3.4. Instalação e Configuração do Servidor Web
Acesso à Instância via SSH: Após a criação da instância, acessamos via SSH utilizando o terminal.
Atualização do Sistema: Atualizamos os pacotes do sistema com os comandos:

`
bash
sudo apt update
sudo apt upgrade
`

#### 3.5. Instalação do Servidor Web: 
Configuramos o servidor web para hospedar o site. Dependendo do servidor utilizado (por exemplo, Nginx, Apache, etc.), os passos podem incluir:

- Instalação do servidor web através do gerenciador de pacotes.
- Configuração dos arquivos de site e permissões.
- Implementação de regras de firewall e segurança.
- Deploy do Site:
O site foi desenvolvido localmente e transferido para a instância EC2.
Os arquivos foram colocados no diretório raiz do servidor web, geralmente localizado em /var/www/html/.

Configurações adicionais, como redirecionamento e otimização, foram realizadas conforme necessário.

A conexão com o banco de dados RDS foi configurada e testada para garantir o funcionamento adequado.

### 🌐 4. Desenvolvimento do Site
O site contém as seguintes seções:
- *Página Inicial:* Introdução ao curso de Redes de Computadores, com informações gerais e objetivos do curso.
- *Sobre o Curso:* Detalhes sobre o conteúdo programático, professores, e metodologia.
- *Materiais e Recursos:* Disponibilização de materiais de estudo, slides, e links úteis.
Contato: Formulário de contato para dúvidas e informações adicionais.

### ✅ 5. Testes e Validação
Realizamos testes de acessibilidade, responsividade e desempenho do site, garantindo que o conteúdo fosse acessível em diferentes dispositivos (desktop, tablet, mobile).

Testamos também a conectividade e desempenho do banco de dados hospedado no RDS.

### 📝 6. Conclusão
O projeto foi concluído com sucesso, e o site está operacional na instância da AWS, com o banco de dados gerenciado pelo Amazon RDS. Ele serve como um portal de informações sobre o curso de Redes de Computadores, facilitando o acesso de alunos e interessados às informações relevantes.

### 🚀 7. Próximos Passos
Com o projeto concluído, vamos continuar fazendo manutenções e monitoramento da instância AWS e do banco de dados RDS, para garantir disponibilidade e desempenho. Além disso, continuaremos atualizando as informações sobre curso em caso de eventuais mudanças.

### 📚 8. Referências
Documentação AWS EC2
