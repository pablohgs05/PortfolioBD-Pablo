# API 1º Semestre - Sistema de Gerenciamento Acadêmico PBLTeX

<div align="center">
  <a href="https://github.com/Porygon-Users/API-Porygon/tree/main">
    <img src="https://img.shields.io/badge/GitHub-Repositório Projeto-181717?style=for-the-badge&logo=github" alt="Repositório">
  </a>
</div>

## Tema do Projeto 📋

**Sistema de Gerenciamento Acadêmico para Metodologia PBL (Problem Based Learning)**

O projeto consiste em um sistema de informação em linha de comando (CLI) desenvolvido em Python para apoiar a instituição PBLTeX, especializada em cursos práticos aplicando a metodologia Problem Based Learning. O sistema gerencia turmas, grupos de alunos, professores, ciclos de entrega e scores parciais, permitindo o cálculo do FEE (Fator de Ensino Evolutivo), a geração de relatórios consolidados e a exportação de dados para análise educacional, tudo executado inteiramente no terminal da IDE sem necessidade de interface web.

## Parceiros Acadêmicos 🎓

- **Programação em Python** - Prof. Responsável pela disciplina de Programação
- **Banco de Dados I** - Prof. Responsável pela disciplina de BD
- **Engenharia de Software I** - Prof. Responsável pela disciplina de ES

## Tecnologias Adotadas 💻

<div align="center">
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original-wordmark.svg" width="100" height="100" alt="Python"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original-wordmark.svg" width="100" height="100" alt="MySQL"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/git/git-original-wordmark.svg" width="100" height="100" alt="Git"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/vscode/vscode-original-wordmark.svg" width="100" height="100" alt="VS Code"/>
</div>

### Descrição das Tecnologias

- **[Python](https://www.python.org/)**: Linguagem de programação interpretada, dinâmica e altamente legível, utilizada para desenvolver toda a lógica de negócio do sistema. Python foi escolhido por sua simplicidade e eficiência no prototipagem rápida de soluções educacionais.

- **[MySQL](https://www.mysql.com/)**: Sistema de gerenciamento de banco de dados relacional de código aberto, utilizado para armazenar de forma estruturada informações sobre alunos, professores, turmas, grupos, ciclos de entrega, scores parciais e relatórios consolidados.

- **[Git](https://git-scm.com/)**: Sistema de controle de versão distribuído utilizado para gerenciar o código-fonte do projeto, permitindo colaboração eficiente entre os membros da equipe através de commits, branches e pull requests.

- **[VS Code](https://code.visualstudio.com/)**: Editor de código-fonte leve e poderoso, utilizado para desenvolvimento, depuração e execução do código Python diretamente no terminal integrado da IDE.

- **[Trello](https://trello.com/)**: Ferramenta de gerenciamento de projetos utilizada para organizar tarefas, sprints e acompanhamento do progresso do desenvolvimento em tempo real.

- **[Microsoft Teams](https://www.microsoft.com/pt-br/microsoft-teams/compare-microsoft-teams-options)**: Plataforma de comunicação e colaboração utilizada para reuniões de sprint, daily standups e discussões técnicas da equipe.

- **[Canva](https://www.canva.com/)**: Ferramenta de design utilizada para criar apresentações visuais, mockups e documentação gráfica do projeto.

---

## Arquitetura e Estrutura do Projeto 🏗️

### Requisitos Funcionais

| Código | Requisito |
|--------|-----------|
| RF1 | Controle de Turmas |
| RF2 | Controle de Grupos de Alunos |
| RF3 | Controle de Alunos |
| RF4 | Carregamento de Alunos (importação em massa) |
| RF5 | Controle de Ciclos de Entrega |
| RF6 | Carregamento de Scores Parciais |
| RF7 | Configuração de Parâmetros Globais |
| RF8 | Exportação de Dados Consolidados e Métricas |
| RF9 | Visibilidades Objetivas de Acompanhamento de Cursos |
| RF10 | Interface de Menu com Todas as Funcionalidades |

### Cronograma de Desenvolvimento

- **Sprint 1** (04/09 - 24/09): Cadastro de alunos e professores, criação de turmas e associações
- **Sprint 2** (25/09 - 15/10): Criação de grupos, fechamento de turmas, validações
- **Sprint 3** (16/10 - 05/11): Atribuição de scores e feedbacks, geração de relatórios de alunos
- **Sprint 4** (06/11 - 26/11): Menu consolidado, exportação de dados, relatórios finais

---

## Contribuições Individuais 🎯

### Desenvolvimento da Lógica de Negócio em Python

Como desenvolvedor principal, fui responsável pela implementação da lógica de negócio do sistema em Python. Desenvolvi módulos para:
- Gerenciamento de entidades (Alunos, Professores, Turmas, Grupos, Ciclos)
- Validação de dados de entrada
- Cálculo do Fator de Ensino Evolutivo (FEE) baseado em scores parciais
- Lógica de agregação de dados por turma e período

Implementei estruturas de dados eficientes utilizando classes Python com características de orientação a objetos, garantindo código modular e reutilizável para diferentes funcionalidades do sistema.

### Interface de Linha de Comando (CLI)

Desenvolvi uma interface completa de linha de comando que permite ao usuário administrador navegar por diferentes menus e executar operações através de opções numeradas. O sistema oferece:
- Menu principal com acesso a todas as funcionalidades
- Submenus contextuais para cada entidade (alunos, turmas, grupos, scores)
- Validação de entrada com mensagens de erro claras
- Feedback visual ao usuário indicando sucesso ou falha das operações
- Navegação simples entre telas do terminal

<details>
  <summary>📝 Exemplo: Estrutura de Menu Principal</summary>

```python
class MenuPrincipal:
    def __init__(self):
        self.opcoes = {
            '1': self.gerenciar_alunos,
            '2': self.gerenciar_professores,
            '3': self.gerenciar_turmas,
            '4': self.gerenciar_grupos,
            '5': self.gerenciar_ciclos,
            '6': self.gerenciar_scores,
            '7': self.gerar_relatorios,
            '8': self.exportar_dados,
            '0': self.sair
        }
    
    def exibir_menu(self):
        print("\n" + "="*50)
        print("SISTEMA DE GERENCIAMENTO ACADÊMICO - PBLTeX")
        print("="*50)
        print("1. Gerenciar Alunos")
        print("2. Gerenciar Professores")
        print("3. Gerenciar Turmas")
        print("4. Gerenciar Grupos")
        print("5. Gerenciar Ciclos de Entrega")
        print("6. Atribuir Scores e Feedbacks")
        print("7. Gerar Relatórios")
        print("8. Exportar Dados Consolidados")
        print("0. Sair")
        print("="*50)
        
    def executar(self):
        while True:
            self.exibir_menu()
            escolha = input("Escolha uma opção: ").strip()
            
            if escolha in self.opcoes:
                self.opcoes[escolha]()
            else:
                print("❌ Opção inválida! Tente novamente.")
    
    def gerenciar_alunos(self):
        print("\n--- GERENCIAR ALUNOS ---")
        print("1. Cadastrar Aluno")
        print("2. Listar Alunos")
        print("3. Atualizar Aluno")
        print("4. Deletar Aluno")
        print("0. Voltar")
        # Implementação dos submenus...
    
    def sair(self):
        print("Encerrando sistema... Até logo!")
        exit()
```

</details>

### Integração com Banco de Dados MySQL

Implementei a camada de acesso a dados que conecta a aplicação Python com o banco de dados MySQL. Desenvolvi:
- Módulo de conexão com tratamento de erros
- Operações CRUD (Create, Read, Update, Delete) para todas as entidades
- Queries otimizadas para cálculos de agregação (somas, médias, contagens)
- Transações para garantir consistência de dados

<details>
  <summary>📝 Exemplo: Classe de Acesso a Dados</summary>

```python
import mysql.connector
from mysql.connector import Error

class DatabaseConnection:
    def __init__(self, host='localhost', user='root', password='', database='pbltex'):
        self.host = host
        self.user = user
        self.password = password
        self.database = database
        self.connection = None
    
    def conectar(self):
        try:
            self.connection = mysql.connector.connect(
                host=self.host,
                user=self.user,
                password=self.password,
                database=self.database
            )
            if self.connection.is_connected():
                print("✅ Conectado ao banco de dados com sucesso!")
                return True
        except Error as e:
            print(f"❌ Erro ao conectar: {e}")
            return False
    
    def executar_query(self, query, params=None):
        try:
            cursor = self.connection.cursor()
            if params:
                cursor.execute(query, params)
            else:
                cursor.execute(query)
            self.connection.commit()
            return True
        except Error as e:
            print(f"❌ Erro ao executar query: {e}")
            return False
    
    def obter_dados(self, query, params=None):
        try:
            cursor = self.connection.cursor(dictionary=True)
            if params:
                cursor.execute(query, params)
            else:
                cursor.execute(query)
            resultado = cursor.fetchall()
            cursor.close()
            return resultado
        except Error as e:
            print(f"❌ Erro ao obter dados: {e}")
            return None
    
    def desconectar(self):
        if self.connection and self.connection.is_connected():
            self.connection.close()
            print("✅ Desconectado do banco de dados.")
```

</details>

### Geração de Relatórios e Exportação de Dados

Implementei funcionalidades para gerar relatórios consolidados em diferentes formatos:
- Relatórios por turma com listagem de alunos, grupos e scores
- Cálculo e exibição do Fator de Ensino Evolutivo (FEE) por aluno e turma
- Exportação de dados consolidados para CSV, permitindo análise posterior em ferramentas externas
- Relatórios de feedback dos professores com consolidação de avaliações

<details>
  <summary>📝 Exemplo: Geração de Relatório</summary>

```python
class RelatorioService:
    def __init__(self, db_connection):
        self.db = db_connection
    
    def gerar_relatorio_turma(self, turma_id):
        query = """
            SELECT a.id, a.nome, g.nome as grupo, 
                   AVG(s.valor) as media_scores,
                   COUNT(s.id) as quantidade_scores
            FROM alunos a
            LEFT JOIN grupos g ON a.grupo_id = g.id
            LEFT JOIN scores s ON a.id = s.aluno_id
            WHERE a.turma_id = %s
            GROUP BY a.id, a.nome, g.nome
            ORDER BY a.nome
        """
        
        alunos = self.db.obter_dados(query, (turma_id,))
        
        print("\n" + "="*70)
        print("RELATÓRIO DE TURMA")
        print("="*70)
        
        if alunos:
            for aluno in alunos:
                fee = self.calcular_fee(aluno['media_scores'], aluno['quantidade_scores'])
                print(f"Aluno: {aluno['nome']}")
                print(f"Grupo: {aluno['grupo'] or 'Não atribuído'}")
                print(f"Média de Scores: {aluno['media_scores']:.2f}")
                print(f"FEE (Fator de Ensino Evolutivo): {fee:.2f}")
                print("-" * 70)
        else:
            print("Nenhum aluno encontrado para esta turma.")
    
    def calcular_fee(self, media_scores, quantidade_scores):
        # Cálculo do FEE baseado em média ponderada
        if quantidade_scores == 0:
            return 0
        return (media_scores * quantidade_scores) / 100
    
    def exportar_dados_csv(self, turma_id, nome_arquivo):
        import csv
        
        query = """
            SELECT a.id, a.nome, a.email, g.nome as grupo, 
                   AVG(s.valor) as media_scores
            FROM alunos a
            LEFT JOIN grupos g ON a.grupo_id = g.id
            LEFT JOIN scores s ON a.id = s.aluno_id
            WHERE a.turma_id = %s
            GROUP BY a.id
        """
        
        alunos = self.db.obter_dados(query, (turma_id,))
        
        if alunos:
            with open(nome_arquivo, 'w', newline='', encoding='utf-8') as csvfile:
                fieldnames = ['ID', 'Nome', 'Email', 'Grupo', 'Média de Scores']
                writer = csv.DictWriter(csvfile, fieldnames=fieldnames)
                
                writer.writeheader()
                for aluno in alunos:
                    writer.writerow({
                        'ID': aluno['id'],
                        'Nome': aluno['nome'],
                        'Email': aluno['email'],
                        'Grupo': aluno['grupo'] or 'N/A',
                        'Média de Scores': f"{aluno['media_scores']:.2f}" if aluno['media_scores'] else "N/A"
                    })
            
            print(f"✅ Dados exportados para {nome_arquivo} com sucesso!")
        else:
            print("❌ Nenhum dado para exportar.")
```

</details>

### Validação de Dados e Tratamento de Erros

Implementei um sistema robusto de validação de entrada que garante:
- Verificação de campos obrigatórios
- Validação de formatos (email, datas, números)
- Detecção de duplicatas e conflitos de dados
- Mensagens de erro informativas em português
- Tratamento gracioso de exceções

---

## Aprendizados Efetivos 📚

Este projeto foi transformador para minha formação como desenvolvedor, proporcionando experiência prática em desenvolvimento de software em Python:

### Programação em Python

Meu primeiro contato profundo com Python consolidou meu entendimento de programação orientada a objetos, tipagem dinâmica, estruturas de dados (listas, dicionários, tuplas) e manipulação de exceções. Aprendi a escrever código Python idiomático e eficiente.

### Integração com Banco de Dados

Trabalhar com MySQL através de Python me ensinou conceitos importantes de:
- Conexão segura com banco de dados
- Prevenção de SQL injection
- Otimização de queries
- Transações e consistência de dados
- Modelagem relacional aplicada

### Desenvolvimento de Interface CLI

Desenvolver uma interface de linha de comando intuitiva e responsiva me preparou para criar aplicações backend robustas. Aprendi a importância de feedback claro ao usuário, validação de entrada e navegação lógica.

### Projeto e Arquitetura de Software

Participei da arquitetura de um sistema com múltiplas camadas (lógica, banco de dados, interface), aprendendo princípios de separação de responsabilidades, modularidade e reutilização de código.

### Metodologia Ágil (Scrum)

Trabalhei em um projeto colaborativo com sprints de 2-3 semanas, participando de planejamento, daily standups e retrospectivas. Aprendi a importância de comunicação clara, divisão de tarefas e entrega incremental de valor.

### Tratamento de Requisitos Complexos

O sistema PBLTeX apresentou requisitos educacionais específicos (cálculo de FEE, gerenciamento de ciclos) que me obrigaram a compreender profundamente o domínio da educação e traduzir necessidades complexas em código.

---

## Competências Desenvolvidas 🏆

### Hard Skills

| Tecnologia/Metodologia | Proficiência | Classificação |
|------------------------|--------------|---------------|
| Python | ⭐⭐⭐⭐☆ | Sei fazer com ajuda |
| MySQL | ⭐⭐⭐⭐☆ | Sei fazer com ajuda |
| SQL (Consultas e JOINs) | ⭐⭐⭐⭐☆ | Sei fazer com ajuda |
| Programação Orientada a Objetos | ⭐⭐⭐⭐☆ | Sei fazer com ajuda |
| Interface CLI (Command Line) | ⭐⭐⭐⭐⭐ | Sei fazer com autonomia |
| Git/Versionamento | ⭐⭐⭐⭐⭐ | Sei fazer com autonomia |
| Modelagem de Dados | ⭐⭐⭐⭐☆ | Sei fazer com ajuda |
| Validação de Dados | ⭐⭐⭐⭐⭐ | Sei fazer com autonomia |
| Scrum/Agile | ⭐⭐⭐⭐⭐ | Sei fazer com autonomia |
| VS Code | ⭐⭐⭐⭐⭐ | Sei fazer com autonomia |

### Soft Skills

| Habilidade | Descrição |
|-----------|-----------|
| **Resolução de Problemas Complexos** | Implementei soluções para requisitos educacionais específicos (cálculo de FEE, gerenciamento de ciclos) e integração com banco de dados. |
| **Pensamento Lógico** | Estruturei a lógica de negócio de forma clara e modular, facilitando manutenção e extensão do sistema. |
| **Comunicação Técnica** | Participei de reuniões de sprint, explicando implementações técnicas e recebendo feedback de stakeholders. |
| **Trabalho em Equipe** | Colaborei com outros desenvolvedores na integração de código e resolução de conflitos no Git. |
| **Adaptabilidade** | Aprendi Python, MySQL e conceitos de metodologia Scrum durante o projeto. |
| **Atenção a Detalhes** | Implementei validações rigorosas para garantir integridade de dados no sistema. |
| **Gestão de Tempo** | Organizei tarefas dentro das sprints para cumprir prazos e entregar incrementos funcionais. |

---

## Como Contribui para o Projeto 🔧

Minha contribuição foi distribuída entre as quatro sprints:

**Sprint 1**: Implementação da estrutura base do projeto, criação de classes para alunos e professores, desenvolvimento da interface de menu inicial e integração básica com MySQL.

**Sprint 2**: Desenvolvimento de funcionalidades de gerenciamento de turmas e grupos, implementação de validações de dados e refatoração do código para melhor modularidade.

**Sprint 3**: Implementação da lógica de atribuição de scores e feedbacks, desenvolvimento de relatórios de alunos e cálculo de estatísticas descritivas.

**Sprint 4**: Consolidação do menu principal, implementação de exportação de dados em CSV, testes finais e documentação do código.

---

## Reflexão Final 💭

Este projeto marcou meu ponto de partida no desenvolvimento de software profissional. Através do "Sistema de Gerenciamento Acadêmico PBLTeX", aprendi que qualidade de software não depende apenas de funcionalidades implementadas, mas também de:
- Código limpo, modular e bem documentado
- Validação rigorosa de dados e tratamento de erros
- Compreensão profunda dos requisitos do negócio
- Comunicação clara com stakeholders e equipe
- Iteração contínua baseada em feedback

Este foi meu primeiro semestre da jornada como desenvolvedor, e as lições aprendidas aqui formam a base sólida para os projetos subsequentes.

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
    <td><a href="https://github.com/pablohgs05/PortfolioBD-Pablo/blob/main/API_4.md">API 4</a></td>
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
