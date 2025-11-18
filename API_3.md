# API 3º Semestre - Ferramenta de Captura e Armazenamento de Notícias Estratégicas

<div align="center">
  <a href="https://github.com/PorygonAPI/Porygon2">
    <img src="https://img.shields.io/badge/GitHub-Repositório Projeto-181717?style=for-the-badge&logo=github" alt="Repositório">
  </a>
</div>

## Tema do Projeto 📋

**Ferramenta de Captura e Armazenamento de Notícias Estratégicas e Dados Relevantes Associados**

A solução proposta visa criar uma aplicação robusta para a coleta automatizada de notícias de múltiplos portais web e APIs públicas, com armazenamento estruturado em banco de dados relacional. O sistema implementa web scraping inteligente, categorização por tags e filtros avançados de pesquisa, permitindo que usuários capturem, organizem e recuperem informações estratégicas de forma eficiente e contextualizada.

## Parceiros Acadêmicos 🎓

- **Programação de Banco de Dados** - Prof.ª Juliana Forin Pasquini Martinez
- **Linguagem de Programação II** - Prof. Lucas Gonçalves Nadalete
- **Laboratório de Desenvolvimento em Banco de Dados III** - Prof. Giuliano Araújo Bertoti

## Tecnologias Adotadas 💻

<div align="center">
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original-wordmark.svg" width="100" height="100" alt="Java"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/spring/spring-original-wordmark.svg" width="100" height="100" alt="Spring Boot"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original-wordmark.svg" width="100" height="100" alt="MySQL"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original-wordmark.svg" width="100" height="100" alt="HTML5"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original-wordmark.svg" width="100" height="100" alt="CSS3"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/figma/figma-original.svg" width="100" height="100" alt="Figma"/>
</div>

### Descrição das Tecnologias

- **[Java 22](https://www.java.com/pt-BR/)**: Linguagem de programação orientada a objetos, multiplataforma e robusta, utilizada para o desenvolvimento do backend da aplicação com suporte a processamento assíncrono e manipulação eficiente de dados.

- **[Spring Boot 3.3.3](https://spring.io/projects/spring-boot)**: Framework para desenvolvimento ágil de aplicações Java, fornecendo componentes como Spring Data JPA para persistência de dados, Spring Web para exposição de APIs REST, e Spring Thymeleaf para renderização de templates HTML no servidor.

- **[MySQL](https://www.mysql.com/)**: Sistema de gerenciamento de banco de dados relacional de código aberto, utilizado para armazenar estruturadamente portais, notícias, APIs, tags e suas relações, com suporte para consultas complexas, índices e otimização de performance.

- **[HTML5](https://developer.mozilla.org/pt-BR/docs/Web/HTML)**: Linguagem de marcação utilizada para estruturar as páginas web, criando uma interface minimalista e semântica que facilita a acessibilidade e a manutenção do código.

- **[CSS3](https://developer.mozilla.org/pt-BR/docs/Web/CSS)**: Linguagem de estilos que define a apresentação visual das páginas web, implementando responsividade e garantindo uma experiência consistente em diferentes dispositivos e resoluções.

- **[Lombok](https://projectlombok.org/)**: Biblioteca Java que reduz a verbosidade do código através de anotações, automatizando a geração de getters, setters, construtores e métodos equals/hashCode nas entidades do projeto.

- **[Jsoup](https://jsoup.org/)**: Biblioteca Java para parsing e manipulação de HTML, essencial para o processo de web scraping que extrai dados dos portais de notícias utilizando seletores CSS.

- **[Jackson](https://github.com/FasterXML/jackson)**: Biblioteca para serialização e desserialização de dados JSON e XML, permitindo a manipulação eficiente de respostas de APIs externas e a geração de respostas estruturadas.

- **[Figma](https://www.figma.com/)**: Ferramenta de design colaborativo utilizada para prototipação das interfaces de usuário, facilitando a visualização e o feedback sobre a estrutura visual da aplicação antes da implementação.

---

## Arquitetura e Estrutura do Projeto 🏗️

### Requisitos Funcionais

| Código | Requisito |
|--------|-----------|
| R1 | Cadastro de Portais de notícias |
| R2 | Cadastro de APIs |
| R3 | Cadastro de Tags |
| R4 | Cadastro de Jornalistas |
| R5 | Processo de web scraping (capturar dados de notícias e APIs) |
| R6 | Indicação de tags relacionadas |
| R7 | Tela de consulta de notícias com filtros |
| R8 | Tela de APIs com filtros |

### Requisitos Não-Funcionais

| Código | Requisito |
|--------|-----------|
| RN1 | Prever grande volume de notícias armazenadas |
| RN2 | Utilizar softwares livres |
| RN3 | Manual do Usuário |
| RN4 | Guia de instalação |
| RN5 | Java (linguagem, frameworks e APIs) |
| RN6 | Documentação API com OpenID |
| RN7 | Modelagem de Banco de Dados relacional |
| RN8 | Aplicação web |
| RN9 | Frontend minimalista |

### Fases de Desenvolvimento

- **Sprint 1** (09/09 - 29/09): Implementação de cadastro de portais e web scraping inicial
- **Sprint 2** (30/09 - 20/10): Cadastro de APIs e filtros por data
- **Sprint 3** (21/10 - 10/11): Sistema de tags e vinculation automática
- **Sprint 4** (11/11 - 01/12): Consultas avançadas por tags e refinamento

---

## Contribuições Individuais 🎯

### Desenvolvimento Backend e Arquitetura

Como desenvolvedor backend responsável pela integração entre banco de dados e lógica de negócios, atuei no design e implementação dos serviços REST da aplicação. Meu foco principal foi garantir que a coleta de dados através de web scraping funcionasse de forma eficiente, sem duplicações e respeitando os agendamentos definidos pelos usuários.

Implementei a lógica de agendamento de tarefas de scraping que respeita as periodicidades (diária, semanal, mensal) configuradas para cada portal e API. Isso envolveu criar mecanismos de verificação de integridade de dados e validação de campos obrigatórios em múltiplos pontos da aplicação.

### Otimização de Consultas e Banco de Dados

Participei ativamente na modelagem do banco de dados relacional, desenhando a estrutura de tabelas, índices e relacionamentos para suportar:
- Armazenamento de portais com configurações de scraping
- Relacionamentos muitos-para-muitos entre notícias e tags
- Histórico de APIs e seus dados associados
- Queries otimizadas com junções (JOINs), subconsultas e agrupamentos

### Integração de Web Scraping e Manipulação de Dados

Implementei rotinas robustas de web scraping utilizando Jsoup, com tratamento de exceções e validação de seletores HTML. A solução captura título, data, conteúdo e autor das notícias, aplicando automaticamente as tags configuradas no portal com base na análise do conteúdo.

<details>
  <summary>📝 Exemplo: Classe de Serviço de Web Scraping</summary>

```java
@Service
public class WebScrapingService {
    
    @Autowired
    private PortalRepository portalRepository;
    
    @Autowired
    private NotíciaRepository notíciaRepository;
    
    public void executarScrapingAgendado(Long portalId) {
        Optional<Portal> portalOpt = portalRepository.findById(portalId);
        
        if (portalOpt.isPresent()) {
            Portal portal = portalOpt.get();
            
            try {
                Document doc = Jsoup.connect(portal.getUrl())
                    .userAgent("Mozilla/5.0")
                    .timeout(10000)
                    .get();
                
                Elements notíciaElements = doc.select(portal.getSeletorNotícia());
                
                notíciaElements.forEach(element -> {
                    String titulo = element.select(portal.getSeletorTítulo()).text();
                    String conteudo = element.select(portal.getSeletorConteúdo()).text();
                    String data = element.select(portal.getSeletorData()).text();
                    
                    Notícia noticia = new Notícia();
                    noticia.setTitulo(titulo);
                    noticia.setConteudo(conteudo);
                    noticia.setData(parseData(data));
                    noticia.setPortal(portal);
                    
                    aplicarTags(noticia, portal);
                    notíciaRepository.save(noticia);
                });
                
            } catch (IOException e) {
                log.error("Erro ao executar scraping para portal: " + portalId, e);
            }
        }
    }
    
    private void aplicarTags(Notícia noticia, Portal portal) {
        portal.getTags().forEach(tag -> {
            if (noticia.getConteudo().toLowerCase()
                    .contains(tag.getNome().toLowerCase()) ||
                noticia.getTitulo().toLowerCase()
                    .contains(tag.getNome().toLowerCase())) {
                noticia.adicionarTag(tag);
            }
        });
    }
}
```

</details>

### Desenvolvimento das Camadas de Visualização

Participei na criação das interfaces HTML e CSS seguindo os princípios de minimalismo e usabilidade. Implementei:
- Formulários de cadastro para portais e APIs com validação frontend
- Tabelas dinâmicas com filtros por tag, data e palavra-chave
- Componentes de busca elástica para seleção de tags
- Interfaces responsivas que se adaptam a diferentes tamanhos de tela

<details>
  <summary>📝 Exemplo: Template HTML para Consulta de Notícias</summary>

```html
<div class="container mt-5">
    <h2>Consultar Notícias</h2>
    
    <form id="filtroForm" class="mb-4">
        <div class="row">
            <div class="col-md-6">
                <label for="tags">Filtrar por Tags:</label>
                <input type="text" id="tagSearch" class="form-control" 
                       placeholder="Digite a tag...">
                <div id="tagSuggestions" class="list-group mt-2"></div>
                <div id="selectedTags" class="mt-3"></div>
            </div>
            
            <div class="col-md-6">
                <label for="dataInicio">Intervalo de Datas:</label>
                <input type="date" id="dataInicio" class="form-control">
                <input type="date" id="dataFim" class="form-control mt-2">
            </div>
        </div>
        
        <button type="submit" class="btn btn-primary mt-3">Buscar</button>
    </form>
    
    <table class="table table-striped" id="noticiasTable">
        <thead>
            <tr>
                <th>Título</th>
                <th>Portal</th>
                <th>Data</th>
                <th>Tags</th>
            </tr>
        </thead>
        <tbody id="noticiasBody">
        </tbody>
    </table>
</div>
```

</details>

---

## Aprendizados Efetivos 📚

Este projeto foi transformador para minha formação como desenvolvedor, proporcionando experiência prática em desafios reais de software:

### Persistência e Modelagem de Dados

O projeto exigiu profundo entendimento de modelagem relacional e otimização de consultas. Trabalhei com índices de banco de dados, relacionamentos complexos muitos-para-muitos e estratégias de normalização para garantir integridade e performance em cenários com volumes significativos de notícias.

### Web Scraping e Processamento Assíncrono

Aprendi a lidar com web scraping em escala, implementando tratamento de erros, retry logic e agendamento de tarefas. Compreendi os desafios de trabalhar com dados de fontes externas: formato inconsistente, disponibilidade intermitente e estruturas HTML variáveis.

### Arquitetura de Aplicações Web Escaláveis

Participei da implementação de uma arquitetura em camadas com separação clara entre controllers, services e repositories. Isso preparou-me para trabalhar em projetos corporativos onde a manutenibilidade e escalabilidade são críticas.

### Comunicação Ágil e Trabalho em Equipe

O projeto utilizou Scrum com sprints de aproximadamente 2 semanas. Aprendi a importância de:
- Comunicação clara de requisitos através de user stories
- Planejamento realista com story points
- Retrospecitivas que melhoram continuamente o processo
- Integração contínua entre backend e frontend

### Performance e Análise de Algoritmos

Com um volume crescente de notícias, foquei em otimizar queries e processos de scraping. Isso envolveu análise de planos de execução SQL, criação de índices estratégicos e refatoração de código para reduzir complexidade algorítmica.

---

## Competências Desenvolvidas 🏆

### Hard Skills

| Tecnologia/Metodologia | Proficiência | Classificação |
|------------------------|--------------|---------------|
| Java | ⭐⭐⭐⭐☆ | Sei fazer com ajuda |
| Spring Boot | ⭐⭐⭐⭐☆ | Sei fazer com ajuda |
| MySQL | ⭐⭐⭐⭐☆ | Sei fazer com ajuda |
| SQL Avançado (JOINs, Subconsultas) | ⭐⭐⭐⭐☆ | Sei fazer com ajuda |
| HTML5 | ⭐⭐⭐⭐⭐ | Sei fazer com autonomia |
| CSS3 | ⭐⭐⭐⭐⭐ | Sei fazer com autonomia |
| Web Scraping (Jsoup) | ⭐⭐⭐⭐☆ | Sei fazer com ajuda |
| REST APIs | ⭐⭐⭐⭐☆ | Sei fazer com ajuda |
| Git/Versionamento | ⭐⭐⭐⭐☆ | Sei fazer com autonomia |
| Scrum/Agile | ⭐⭐⭐⭐⭐ | Sei fazer com autonomia |

### Soft Skills

| Habilidade | Descrição |
|-----------|-----------|
| **Resolução de Problemas Complexos** | Enfrentei desafios com web scraping em diferentes estruturas HTML e implementei soluções robustas com tratamento de exceções. |
| **Pensamento Crítico** | Analisei requisitos de negócio e sugeri otimizações de banco de dados para suportar crescimento de dados. |
| **Comunicação Técnica** | Documentei seletores HTML para os usuários, facilitando a configuração de novos portais. |
| **Trabalho em Equipe** | Colaborei na integração backend-frontend, participei de daily standups e retrospectivas. |
| **Adaptabilidade** | Aprendi múltiplas tecnologias novas durante o projeto (Spring Boot, Jsoup, Thymeleaf). |
| **Atenção a Detalhes** | Validei dados em múltiplas camadas para garantir integridade durante scraping e armazenamento. |
| **Gestão de Tempo** | Mantive ritmo de desenvolvimento em sprints curtas com deadlines definidos. |

---

## Tecnologias Utilizadas (Resumo Visual) 📊

- **Backend**: Java 54.8%
- **Frontend**: HTML 44.2%
- **Estilos**: CSS 1.0%

### Stack Técnico Completo

- **Linguagem Principal**: Java 22
- **Framework Web**: Spring Boot 3.3.3 (Spring Data JPA, Spring Web, Spring Thymeleaf)
- **Banco de Dados**: MySQL
- **Web Scraping**: Jsoup
- **Serialização**: Jackson (JSON/XML)
- **Redução de Boilerplate**: Lombok
- **Controle de Versão**: Git
- **Metodologia**: Scrum Agile
- **Design**: Figma

---

## Como Contribui para o Projeto 🔧

Minha contribuição foi distribuída entre as quatro sprints:

**Sprint 1-2**: Implementação do serviço de web scraping, models de Entity (Portal, Notícia, API, Tag) e persistência com Spring Data JPA.

**Sprint 2-3**: Desenvolvimento de endpoints REST para cadastro e edição de portais/APIs, validações de negócio e integração com Jsoup.

**Sprint 3-4**: Implementação da lógica de vinculação automática de tags, otimização de queries, interfaces de filtro e busca.

---

## Reflexão Final 💭

Este projeto consolidou meu entendimento de como sistemas web funcionam de ponta a ponta. Através da "Ferramenta de Captura e Armazenamento de Notícias Estratégicas", aprendi que qualidade não vem apenas de código limpo, mas também de:
- Compreensão profunda do domínio do negócio
- Design de banco de dados pensado em escalabilidade
- Interfaces que refletem as necessidades reais dos usuários
- Processos ágeis que permitem feedback rápido

Estou pronto para aplicar estas competências em projetos cada vez mais complexos e desafiadores.

---

<div align="center">

## Navegação entre Projetos 🔗

<table align="center" style="font-family: roboto; font-size: 14px; text-align: left;">
  <tr>
    <td>1º Semestre:</td>
    <td><a href="https://github.com/pablohgs05/PortfolioBD-Pablo/blob/main/API_1.md">(API 1)</a></td>
  </tr>
  <tr>
    <td>2º Semestre:</td>
    <td><a href="https://github.com/pablohgs05/PortfolioBD-Pablo/blob/main/API_2.md">Sistema de Análise e Gestão de Dados Climáticos</a></td>
  </tr>
  <tr>
    <td>3º Semestre:</td>
    <td><a href="https://github.com/pablohgs05/PortfolioBD-Pablo/blob/main/API_3.md">Ferramenta de Captura e Armazenamento de Notícias Estratégicas</a></td>
  </tr>
  <tr>
    <td>4º Semestre:</td>
    <td><a href="https://github.com/pablohgs05/PortfolioBD-Pablo/blob/main/API_4.md">(API 4)</a></td>
  </tr>
  <tr>
    <td>5º Semestre:</td>
    <td><a href="https://github.com/pablohgs05/PortfolioBD-Pablo/blob/main/API_5.md">(API 5)</a></td>
  </tr>
  <tr>
    <td>6º Semestre:</td>
    <td><a href="https://github.com/pablohgs05/PortfolioBD-Pablo/blob/main/API_6.md">(API 6)</a></td>
  </tr>
</table>

</div>
