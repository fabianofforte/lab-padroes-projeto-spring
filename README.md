Lab Padrões de Projeto Spring

📋 Visão Geral
Projeto desenvolvido durante o lab "Explorando Padrões de Projetos na Prática com Java" da Digital Innovation One. Implementação prática de padrões de projeto utilizando o ecossistema Spring, com foco em boas práticas de desenvolvimento e arquitetura de software.

🎯 Padrões de Projeto Implementados
Padrão	Implementação	Descrição
Singleton	@Service, @Component	Beans gerenciados pelo Spring com única instância
Strategy	JpaRepository	Abstração de operações de banco de dados
Facade	ClienteService	Fachada que integra subsistemas (API ViaCEP + H2)

🛠️ Tecnologias
Java 21 - Lógica de negócio
Spring Boot 4.0.3 - Framework principal
Spring Data JPA - Persistência
Spring Cloud OpenFeign - Cliente HTTP
H2 Database - Banco em memória
Maven - Gerenciamento de dependências
Swagger/OpenAPI - Documentação interativa

🚀 Execução
Pré-requisitos
Java JDK 21

Maven 3.9+

Comandos
bash
# Compilar
mvn clean install

# Executar
mvn spring-boot:run
URLs
Serviço	URL
API	http://localhost:8080
Swagger	http://localhost:8080/swagger-ui.html
H2 Console	http://localhost:8080/h2-console

🧩 Arquitetura
text
┌──────────┐    ┌──────────┐    ┌──────────┐    ┌──────────┐
│ Cliente  │───▶│Controller│───▶│ Service  │───▶│Repository│
│ (HTTP)   │◀───│   REST   │◀───│ (Facade) │◀───│   (JPA)  │
└──────────┘    └──────────┘    └────┬─────┘    └────┬─────┘
│               │
▼               ▼
┌──────────┐    ┌──────────┐
│ViaCEP API│    │H2 Database│
│(Externa) │    │(Memória) │
└──────────┘    └──────────┘

⚙️ Configurações Principais
properties
# Banco H2
spring.datasource.url=jdbc:h2:mem:testdb
spring.h2.console.enabled=true

# JPA
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true

# Swagger
springdoc.swagger-ui.path=/swagger-ui.html


📚 Conceitos Aplicados
✅ Injeção de Dependência

✅ Beans do Spring (Singleton)

✅ Spring Data JPA (Strategy/Repository)

✅ Fachada para integração com API externa

✅ Documentação automática com Swagger

✅ Banco de dados em memória para testes

📄 Licença
MIT

Digital Innovation One - Lab de Padrões de Projeto com Spring

