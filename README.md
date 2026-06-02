
# 🎵 Screen Sound Músicas - Spring Boot & JPA

O **Screen Sound** é uma aplicação voltada para o gerenciamento de catálogos musicais de artistas e bandas. Desenvolvido com a arquitetura do ecossistema **Spring**, o projeto utiliza persistência em banco de dados relacional e integrações externas para automatizar consultas informativas sobre a história dos artistas.

## 🚀 Funcionalidades do Sistema

* **Cadastro de Artistas:** Registro modular de artistas categorizados por enumeradores (`SOLO`, `DUPLA` ou `BANDA`).
* **Vínculo Relacional de Músicas:** Sistema de cadastro de faixas associadas diretamente a um artista previamente armazenado em banco de dados.
* **Listagem Abrangente:** Varredura completa no banco de dados para recuperar e exibir as hierarquias de artistas e suas respectivas faixas.
* **Consultas Customizadas com JPQL:** Mecanismo de busca avançado que localiza músicas com base em filtros parciais ou buscas textuais insensíveis a maiúsculas/minúsculas (`ILIKE`).
* **Integração com IA (ChatGPT API):** Módulo de serviço inteligente que consome dados externos para coletar curiosidades ou biografias completas sobre o artista pesquisado.

---

## 🛠️ Stack Tecnológica & Conceitos Aplicados

* **Spring Boot:** Framework base para a inicialização automatizada, gerenciamento de dependências e inversão de controle (`@Autowired`).
* **Spring Data JPA & Hibernate:** Camada de abstração do banco de dados relacional, utilizando herança da interface `JpaRepository` para eliminação de códigos SQL manuais (CRUD automatizado).
* **Mapeamento Objeto-Relacional (ORM):** Gerenciamento de relacionamentos de tabelas através de anotações JPA, aplicando o conceito de `1:N` (Um artista para muitas músicas) com a diretriz `@ManyToOne` na entidade filha.
* **Queries Derivadas & JPQL:** Criação de consultas customizadas combinando assinaturas de métodos declarativos (`findByNomeContainingIgnoreCase`) e consultas explícitas mapeadas via anotação `@Query`.
* **Classes Enumeradas (Enum):** Uso de tipos restritos (`TipoArtista`) para garantir a consistência e integridade dos dados inseridos no domínio da aplicação.
* **Interfaces Command Line:** Implementação da interface `CommandLineRunner` do Spring Boot para disparar o menu interativo via console logo após o bootstrap completo do framework.

---

## 📂 Estrutura Arquitetural do Projeto

```text
├── src/main/java/br/com/alura/screensound/
│   ├── ScreensoundApplication.java  # Ponto de entrada do Spring e inicializador
│   ├── principal/
│   │   └── Principal.java           # Menu interativo de console e orquestrador de fluxo
│   ├── model/
│   │   ├── Artista.java             # Entidade JPA principal (Tabela Artistas)
│   │   ├── Musica.java              # Entidade JPA relacionada (Tabela Musicas - @ManyToOne)
│   │   └── TipoArtista.java         # Enumerador de classificação (SOLO/DUPLA/BANDA)
│   ├── repository/
│   │   └── ArtistaRepository.java   # Interface de persistência de dados (Queries JPA/JPQL)
│   └── service/
│       └── ConsultaChatGPT.java     # Serviço responsável pela comunicação com a API de IA

```

---

## 💻 Como Executar a Aplicação

### Pré-requisitos

* Java JDK 17 ou superior.
* Gerenciador de dependências (Maven ou Gradle).
* Banco de dados configurado no arquivo `application.properties` da aplicação (Ex: PostgreSQL ou MySQL).
* Uma chave de API da OpenAI configurada em suas variáveis de ambiente (caso queira utilizar a consulta ao ChatGPT).

### Inicialização

1. Clone este repositório em sua máquina local.
2. Certifique-se de preencher as credenciais corretas do seu banco de dados no arquivo de propriedades do Spring.
3. Execute o projeto diretamente através de sua IDE favorita (IntelliJ IDEA, Eclipse, VS Code) executando a classe `ScreensoundApplication.java` ou via terminal utilizando o wrapper do Maven:
```bash
./mvnw spring-boot:run

```



---

💡 *Projeto avançado focado no domínio de persistência de dados com Spring Data JPA, mapeamento ORM e consumo de serviços de inteligência artificial pela Alura.*

```

```
