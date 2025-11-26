# API 2º Semestre - Sistema de Análise e Gestão de Dados Climáticos

<div align="center">
  <a href="https://github.com/VCCorpTeam/Leitor-de-clima">
    <img src="https://img.shields.io/badge/GitHub-Repositório Projeto-181717?style=for-the-badge&logo=github" alt="Repositório">
  </a>
</div>

## Tema do Projeto 📋

**Sistema de Análise e Gestão de Dados Climáticos - ViraCorp**

O projeto consiste em um sistema desktop desenvolvido em Java para processar, armazenar e analisar dados climáticos provenientes de múltiplas estações meteorológicas no estado de São Paulo. A solução permite o carregamento de arquivos CSV contendo variáveis climáticas (temperatura, umidade, precipitação), validação de dados com detecção de registros suspeitos, geração de relatórios estatísticos por cidade e período, além de cálculos para visualização de gráficos boxplot, fornecendo uma visão analítica e consolidada das condições climáticas regionais.

## Tecnologias Adotadas 💻

<div align="center">
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original-wordmark.svg" width="100" height="100" alt="Java"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original-wordmark.svg" width="100" height="100" alt="MySQL"/>
  <img src="https://upload.wikimedia.org/wikipedia/en/c/cc/JavaFX_Logo.png" width="100" height="100" alt="JavaFX"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/git/git-original-wordmark.svg" width="100" height="100" alt="Git"/>
</div>

### Descrição das Tecnologias

- **[Java](https://www.java.com/pt-BR/)**: Linguagem de programação orientada a objetos, robusta e multiplataforma, utilizada para desenvolver toda a lógica de negócio do sistema, incluindo processamento de arquivos CSV, validação de dados e cálculos estatísticos.

- **[JavaFX](https://openjfx.io/)**: Framework para desenvolvimento de interfaces gráficas (GUI) em Java, permitindo a criação de uma aplicação desktop intuitiva e visualmente organizada, facilitando a interação do usuário com o sistema de análise climática.

- **[MySQL](https://www.mysql.com/)**: Sistema de gerenciamento de banco de dados relacional de código aberto, utilizado para armazenar de forma estruturada os dados climáticos, informações sobre estações meteorológicas, cidades, unidades de medida e registros suspeitos.

- **[Git](https://git-scm.com/)**: Sistema de controle de versão distribuído utilizado para gerenciar o código-fonte do projeto, permitindo colaboração eficiente entre os membros da equipe e rastreamento de mudanças ao longo do desenvolvimento.

- **[IntelliJ IDEA](https://www.jetbrains.com/idea/)**: IDE (Integrated Development Environment) utilizada para o desenvolvimento em Java, oferecendo recursos avançados de depuração, refatoração de código e integração com Git.

- **[Discord](https://discord.com/)**: Ferramenta de comunicação em tempo real utilizada pela equipe para reuniões diárias (daily standups), discussões técnicas e alinhamento de tarefas durante o desenvolvimento do projeto.

---

## Arquitetura e Estrutura do Projeto 🏗️

### Requisitos Funcionais

| Prioridade | Função | Descrição |
|------------|--------|-----------|
| 1 | Leitura de Arquivos CSV | Carregar e validar arquivos CSV contendo dados climáticos de estações meteorológicas |
| 2 | Diagrama de Classes | Elaborar diagrama de classes representando a estrutura do sistema e relações entre entidades |
| 3 | Gerenciamento de Estações e Cidades | Visualizar, adicionar, modificar e excluir informações sobre estações, cidades e unidades de medida |
| 4 | Modelagem de Banco de Dados | Modelar o banco de dados para armazenar dados climáticos de forma eficiente |
| 5 | Interface de Usuário (UI) | Desenvolver interface visual para facilitar interação do usuário com o sistema |
| 6 | Identificação de Cidades | Extrair nome da cidade a partir do arquivo CSV e associá-lo aos dados |
| 7 | Unificação de Dados | Unificar dados de múltiplas estações meteorológicas por cidade |
| 8 | Implementação MySQL | Configurar e implementar banco de dados MySQL conforme modelo definido |
| 9 | Tratamento de Registros Suspeitos | Revisar, corrigir ou excluir registros com valores fora dos padrões normais |
| 10 | Relatório de Médias | Gerar relatórios de médias das variáveis climáticas por cidade e período |
| 11 | Boxplot | Calcular elementos necessários para plotagem de gráficos boxplot |
| 12 | Ajustes e Melhorias | Realizar ajustes finais e melhorias de usabilidade |
| 13 | Documentação | Preparar documentação completa do sistema |

### Cronograma de Desenvolvimento

- **Sprint 1** (25/03 - 14/04/2024): Modelagem do banco de dados e diagrama de classes
- **Sprint 2** (15/04 - 05/05/2024): Leitura de CSV, validação e detecção de registros suspeitos
- **Sprint 3** (06/05 - 26/05/2024): Interface gráfica, gerenciamento de entidades e unificação de dados
- **Sprint 4** (27/05 - 16/06/2024): Relatórios estatísticos, cálculos de boxplot e documentação final

---

## Contribuições Individuais 🎯

### Desenvolvimento Backend e Lógica de Negócio

Como desenvolvedor backend, atuei na implementação da lógica de carregamento e processamento de arquivos CSV. Fui responsável por desenvolver os parsers que leem os dados climáticos, identificam as estações a partir do nome do arquivo e armazenam cada variável climática (temperatura, umidade, precipitação, velocidade do vento) em registros separados no banco de dados.

Implementei o sistema de validação de dados que identifica registros suspeitos com base em limites pré-definidos (por exemplo, temperatura acima de 60°C ou abaixo de -20°C). Esses registros são armazenados em uma tabela separada para revisão manual, permitindo ao usuário corrigir ou excluir conforme necessário.

### Modelagem e Implementação do Banco de Dados

Participei ativamente da modelagem do banco de dados MySQL, definindo as seguintes entidades principais:
- **Estações Meteorológicas**: armazenam informações sobre cada estação de coleta
- **Cidades**: associam estações a municípios específicos
- **Unidades de Medida**: padronizam as unidades utilizadas para cada variável climática
- **Registros Climáticos**: armazenam os dados válidos de forma normalizada
- **Registros Suspeitos**: mantêm dados que requerem revisão manual

Implementei queries SQL otimizadas para cálculo de médias e estatísticas descritivas (mínimo, máximo, quartis) necessárias para a geração de relatórios e gráficos boxplot.

### Desenvolvimento da Interface Gráfica (JavaFX)

Colaborei na construção da interface gráfica utilizando JavaFX, criando telas para:
- Upload e visualização de arquivos CSV carregados
- Gerenciamento de estações meteorológicas, cidades e unidades de medida
- Revisão e correção de registros suspeitos
- Geração de relatórios de médias por cidade e período selecionado

Implementei componentes visuais como tabelas dinâmicas, filtros de data, seletores de cidade e painéis de feedback para alertar o usuário sobre erros ou inconsistências nos dados carregados.

<details>
  <summary>📝 Exemplo: Classe de Processamento de CSV</summary>

```java
public class CSVProcessor {
    
    private EstacaoRepository estacaoRepository;
    private RegistroClimaticoRepository registroRepository;
    private RegistroSuspeitoRepository suspeitoRepository;
    
    public void processarArquivoCSV(File arquivo) throws IOException {
        String nomeArquivo = arquivo.getName();
        String nomeCidade = extrairNomeCidade(nomeArquivo);
        String nomeEstacao = extrairNomeEstacao(nomeArquivo);
        
        Estacao estacao = estacaoRepository.findByNome(nomeEstacao)
            .orElseGet(() -> criarNovaEstacao(nomeEstacao, nomeCidade));
        
        try (BufferedReader reader = new BufferedReader(new FileReader(arquivo))) {
            String linha;
            reader.readLine(); // Pula cabeçalho
            
            while ((linha = reader.readLine()) != null) {
                String[] valores = linha.split(",");
                
                LocalDateTime dataHora = LocalDateTime.parse(valores[0]);
                double temperatura = Double.parseDouble(valores[1]);
                double umidade = Double.parseDouble(valores[2]);
                double precipitacao = Double.parseDouble(valores[3]);
                double velocidadeVento = Double.parseDouble(valores[4]);
                
                // Validação e armazenamento de temperatura
                if (isValorSuspeito(temperatura, -20, 60)) {
                    suspeitoRepository.save(
                        new RegistroSuspeito(estacao, dataHora, "TEMPERATURA", temperatura)
                    );
                } else {
                    registroRepository.save(
                        new RegistroClimatico(estacao, dataHora, "TEMPERATURA", temperatura)
                    );
                }
                
                // Repetir processo para umidade, precipitação, velocidade do vento...
            }
        }
    }
    
    private boolean isValorSuspeito(double valor, double min, double max) {
        return valor < min || valor > max;
    }
    
    private String extrairNomeCidade(String nomeArquivo) {
        // Lógica para extrair cidade do nome do arquivo
        return nomeArquivo.split("_")[0];
    }
    
    private String extrairNomeEstacao(String nomeArquivo) {
        // Lógica para extrair estação do nome do arquivo
        return nomeArquivo.replace(".csv", "").split("_")[1];
    }
}
```

</details>

### Geração de Relatórios Estatísticos

Implementei a lógica para geração de dois tipos principais de relatórios:

1. **Relatório de Situação (Instantâneo)**: apresenta os valores médios das últimas medidas para cada cidade
2. **Relatório de Médias por Período**: permite ao usuário selecionar cidade e intervalo de tempo, retornando médias horárias das variáveis climáticas

Além disso, desenvolvi métodos para calcular os elementos necessários para plotagem de gráficos boxplot (mínimo, primeiro quartil, mediana, terceiro quartil, máximo) com base nos dados de uma estação em uma data específica.

<details>
  <summary>📝 Exemplo: Geração de Relatório de Médias</summary>

```java
public class RelatorioService {
    
    @Autowired
    private RegistroClimaticoRepository registroRepository;
    
    public RelatorioMedias gerarRelatorioMedias(String cidade, LocalDate inicio, LocalDate fim) {
        List<RegistroClimatico> registros = registroRepository
            .findByCidadeAndDataHoraBetween(cidade, inicio.atStartOfDay(), fim.atTime(23, 59));
        
        Map<String, DoubleSummaryStatistics> estatisticasPorVariavel = registros.stream()
            .collect(Collectors.groupingBy(
                RegistroClimatico::getVariavel,
                Collectors.summarizingDouble(RegistroClimatico::getValor)
            ));
        
        RelatorioMedias relatorio = new RelatorioMedias();
        relatorio.setCidade(cidade);
        relatorio.setPeriodo(inicio + " a " + fim);
        relatorio.setTemperaturaMedia(
            estatisticasPorVariavel.get("TEMPERATURA").getAverage()
        );
        relatorio.setUmidadeMedia(
            estatisticasPorVariavel.get("UMIDADE").getAverage()
        );
        relatorio.setPrecipitacaoTotal(
            estatisticasPorVariavel.get("PRECIPITACAO").getSum()
        );
        
        return relatorio;
    }
    
    public ElementosBoxplot calcularElementosBoxplot(String estacao, LocalDate data) {
        List<RegistroClimatico> registros = registroRepository
            .findByEstacaoAndData(estacao, data);
        
        List<Double> valores = registros.stream()
            .map(RegistroClimatico::getValor)
            .sorted()
            .collect(Collectors.toList());
        
        int n = valores.size();
        ElementosBoxplot boxplot = new ElementosBoxplot();
        boxplot.setMinimo(valores.get(0));
        boxplot.setPrimeiroQuartil(valores.get(n / 4));
        boxplot.setMediana(valores.get(n / 2));
        boxplot.setTerceiroQuartil(valores.get(3 * n / 4));
        boxplot.setMaximo(valores.get(n - 1));
        
        return boxplot;
    }
}
```

</details>

---

## Aprendizados Efetivos 📚

Este projeto foi fundamental para consolidar minha compreensão de desenvolvimento de software orientado a objetos e gestão de dados:

### Processamento de Dados em Larga Escala

Aprendi a lidar com grandes volumes de dados provenientes de múltiplas fontes (arquivos CSV de diferentes estações), implementando estratégias de parsing eficiente, validação em tempo de execução e armazenamento normalizado em banco de dados relacional.

### Validação e Tratamento de Dados Inconsistentes

O projeto me ensinou a importância de validar dados de entrada e implementar mecanismos de detecção de anomalias. Desenvolvi lógica para identificar registros suspeitos e oferecer ao usuário a possibilidade de correção ou exclusão, garantindo a qualidade dos dados armazenados.

### Desenvolvimento de Interfaces Gráficas com JavaFX

Trabalhei pela primeira vez com JavaFX para criar interfaces desktop interativas. Aprendi a utilizar componentes como TableView, ComboBox, DatePicker e Charts, além de implementar a arquitetura MVC (Model-View-Controller) para separar a lógica de negócio da apresentação.

### Modelagem de Banco de Dados Relacional

Participei da modelagem completa do banco de dados, desde a definição de entidades até a implementação de relacionamentos (1:N, N:M) e índices para otimização de consultas. Isso consolidou meu entendimento de normalização e boas práticas de design de banco de dados.

### Estatística Descritiva e Análise de Dados

Implementei cálculos estatísticos como médias, quartis e elementos de boxplot, aplicando conhecimentos matemáticos à programação. Isso ampliou minha visão sobre como a programação pode ser utilizada para análise de dados científicos.

### Trabalho em Equipe e Metodologia Ágil (Scrum)

Participei de um projeto colaborativo utilizando Scrum, com sprints de 2-3 semanas, daily standups, planejamento de tarefas e retrospectivas. Aprendi a importância da comunicação clara, divisão de responsabilidades e integração contínua do código.

---

## Competências Desenvolvidas 🏆

### Hard Skills

| Tecnologia/Metodologia | Proficiência | Classificação |
|------------------------|--------------|---------------|
| Java | ⭐⭐⭐⭐☆ | Sei fazer com ajuda |
| JavaFX | ⭐⭐⭐⭐☆ | Sei fazer com ajuda |
| MySQL | ⭐⭐⭐⭐☆ | Sei fazer com ajuda |
| SQL (Consultas e JOINs) | ⭐⭐⭐⭐☆ | Sei fazer com ajuda |
| Git/Versionamento | ⭐⭐⭐⭐⭐ | Sei fazer com autonomia |
| Processamento de CSV | ⭐⭐⭐⭐⭐ | Sei fazer com autonomia |
| Modelagem de Dados | ⭐⭐⭐⭐☆ | Sei fazer com ajuda |
| Estatística Descritiva | ⭐⭐⭐⭐☆ | Sei fazer com ajuda |
| Scrum/Agile | ⭐⭐⭐⭐⭐ | Sei fazer com autonomia |
| IntelliJ IDEA | ⭐⭐⭐⭐⭐ | Sei fazer com autonomia |

### Soft Skills

| Habilidade | Descrição |
|-----------|-----------|
| **Resolução de Problemas Complexos** | Implementei soluções para validação de dados inconsistentes e detecção automática de anomalias em grandes volumes de registros climáticos. |
| **Pensamento Analítico** | Analisei requisitos de negócio e traduzi-os em modelos de dados e lógica de processamento estatístico. |
| **Comunicação Técnica** | Participei de reuniões diárias e apresentações de sprint, comunicando claramente o progresso e desafios enfrentados. |
| **Trabalho em Equipe** | Colaborei com outros desenvolvedores na integração de código, resolução de conflitos e revisão de pull requests. |
| **Adaptabilidade** | Aprendi JavaFX e conceitos de estatística descritiva durante o projeto para atender aos requisitos. |
| **Atenção a Detalhes** | Validei dados em múltiplas etapas (parsing, armazenamento, cálculos) para garantir precisão e confiabilidade. |
| **Gestão de Tempo** | Organizei minhas tarefas dentro das sprints para cumprir prazos e entregar funcionalidades completas. |

---

## Como Contribui para o Projeto 🔧

Minha contribuição foi distribuída entre as quatro sprints:

**Sprint 1**: Participação na modelagem do banco de dados MySQL e criação do diagrama de classes UML.

**Sprint 2**: Implementação da lógica de leitura de arquivos CSV, validação de dados e detecção de registros suspeitos.

**Sprint 3**: Desenvolvimento de componentes da interface gráfica JavaFX para gerenciamento de estações, cidades e revisão de registros suspeitos.

**Sprint 4**: Implementação de relatórios estatísticos (médias por cidade e período) e cálculos de elementos para boxplot, além de testes e documentação final.

---

## Reflexão Final 💭

Este projeto foi uma experiência enriquecedora que consolidou minha base em programação orientada a objetos, manipulação de dados e desenvolvimento de interfaces gráficas. Através do "Sistema de Análise e Gestão de Dados Climáticos", aprendi que um bom software não depende apenas de código funcional, mas também de:
- Modelagem de dados pensada para escalabilidade e integridade
- Validação rigorosa para garantir qualidade dos dados
- Interfaces intuitivas que facilitam a interação do usuário
- Trabalho colaborativo e comunicação constante com a equipe

Estou preparado para aplicar esses conhecimentos em projetos futuros que envolvam processamento de dados, análise estatística e desenvolvimento de aplicações desktop.

---

## Navegação entre Projetos 🔗

<table align="center" style="font-family: roboto; font-size: 14px; text-align: left;">
  <tr>
    <td>1º Semestre:</td>
    <td><a href="https://github.com/pablohgs05/PortfolioBD-Pablo/blob/main/API_1.md">Sistema de Gerenciamento Acadêmico PBLTeX - Python + CLI</a></td>
  </tr>
  <tr>
    <td>2º Semestre:</td>
    <td><a href="https://github.com/pablohgs05/PortfolioBD-Pablo/blob/main/API_2.md">Sistema de Análise e Gestão de Dados Climáticos - ViraCorp</a></td>
  </tr>
  <tr>
    <td>3º Semestre:</td>
    <td><a href="https://github.com/pablohgs05/PortfolioBD-Pablo/blob/main/API_3.md">Ferramenta de Captura e Armazenamento de Notícias Estratégicas</a></td>
  </tr>
  <tr>
    <td>4º Semestre:</td>
    <td><a href="https://github.com/pablohgs05/PortfolioBD-Pablo/blob/main/API_4.md">Sistema de Processamento e Análise de Imagens Agrícolas - Visiona</a></td>
  </tr>
  <tr>
    <td>5º Semestre:</td>
    <td><a href="https://github.com/pablohgs05/PortfolioBD-Pablo/blob/main/API_5.md">API 5</a></td>
  </tr>
  <tr>
    <td>6º Semestre:</td>
    <td><a href="https://github.com/pablohgs05/PortfolioBD-Pablo/blob/main/API_6.md">API 6</a></td>
  </tr>
</table>

</div>
