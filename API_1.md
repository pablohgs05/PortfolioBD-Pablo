# API 1º Semestre - Sistema de Gerenciamento Acadêmico PBLTeX

<div align="center">
  <a href="https://github.com/Porygon-Users/API-Porygon/tree/main">
    <img src="https://img.shields.io/badge/GitHub-Repositório Projeto-181717?style=for-the-badge&logo=github" alt="Repositório">
  </a>
</div>

## Tema do Projeto 📋

**Sistema de Gerenciamento Acadêmico para Metodologia PBL (Problem Based Learning)**

O projeto consiste em um sistema de informação em linha de comando (CLI) desenvolvido em Python para apoiar a instituição PBLTeX, especializada em cursos práticos aplicando a metodologia Problem Based Learning. O sistema gerencia turmas, grupos de alunos, professores, ciclos de entrega e scores parciais, permitindo o cálculo do FEE (Fator de Ensino Evolutivo), a geração de relatórios consolidados e a exportação de dados para análise educacional, tudo executado inteiramente no terminal da IDE sem necessidade de interface web. Os dados são armazenados em arquivos Excel, permitindo fácil manipulação e compartilhamento.

## Parceiros Acadêmicos 🎓

- **Programação em Python** - Prof. Responsável pela disciplina de Programação
- **Banco de Dados I** - Prof. Responsável pela disciplina de BD
- **Engenharia de Software I** - Prof. Responsável pela disciplina de ES

## Tecnologias Adotadas 💻

<div align="center">
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original-wordmark.svg" width="100" height="100" alt="Python"/>
  <img src="https://cdn-icons-png.flaticon.com/512/732/732220.png" width="100" height="100" alt="Microsoft Excel"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/github/github-original-wordmark.svg" width="100" height="100" alt="GitHub"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/git/git-original-wordmark.svg" width="100" height="100" alt="Git"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/vscode/vscode-original-wordmark.svg" width="100" height="100" alt="VS Code"/>
  <img src="https://cdn.worldvectorlogo.com/logos/trello.svg" width="100" height="100" alt="Trello"/>
</div>

### Descrição das Tecnologias

- **[Python](https://www.python.org/)**: Linguagem de programação interpretada, dinâmica e altamente legível, utilizada para desenvolver toda a lógica de negócio do sistema. Python foi escolhido por sua simplicidade e eficiência no prototipagem rápida de soluções educacionais, com suporte excelente para manipulação de dados.

- **[Microsoft Excel](https://www.microsoft.com/pt-br/microsoft-365/excel)**: Utilizado como base de dados para armazenar e manipular as informações do sistema. Os arquivos .xlsx servem como repositório de dados, permitindo importação e exportação de informações sobre alunos, turmas, ciclos, scores e relatórios consolidados.

- **[GitHub](https://github.com/)**: Plataforma de hospedagem de repositórios Git utilizada para armazenar o código-fonte do projeto, facilitando a colaboração entre os membros da equipe, controle de versão e documentação do projeto.

- **[Git](https://git-scm.com/)**: Sistema de controle de versão distribuído utilizado para gerenciar o código-fonte do projeto, permitindo colaboração eficiente entre os membros da equipe através de commits, branches e pull requests.

- **[VS Code](https://code.visualstudio.com/)**: Editor de código-fonte leve e poderoso, utilizado para desenvolvimento, depuração e execução do código Python diretamente no terminal integrado da IDE.

- **[Trello](https://trello.com/)**: Ferramenta de gerenciamento de projetos utilizada para organizar tarefas, sprints e acompanhamento do progresso do desenvolvimento em tempo real, permitindo uma visão clara das responsabilidades de cada membro da equipe.

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

### Integração com Arquivos Excel

Implementei a camada de acesso a dados que conecta a aplicação Python com arquivos Excel. Desenvolvi:
- Módulo de leitura e escrita de arquivos .xlsx utilizando bibliotecas como openpyxl
- Operações CRUD (Create, Read, Update, Delete) para todas as entidades armazenadas em Excel
- Importação de dados em massa a partir de arquivos Excel
- Exportação de relatórios e dados consolidados em formato Excel
- Tratamento de erros e validação de integridade de dados

<details>
  <summary>📝 Exemplo: Classe de Acesso a Dados com Excel</summary>

```python
import openpyxl
from openpyxl.utils import get_column_letter

class ExcelDataManager:
    def __init__(self, arquivo_excel='dados_pbltex.xlsx'):
        self.arquivo = arquivo_excel
        self.workbook = None
    
    def conectar(self):
        try:
            self.workbook = openpyxl.load_workbook(self.arquivo)
            print("✅ Conectado ao arquivo Excel com sucesso!")
            return True
        except Exception as e:
            print(f"❌ Erro ao conectar ao arquivo: {e}")
            return False
    
    def obter_dados(self, nome_aba, filtro=None):
        try:
            worksheet = self.workbook[nome_aba]
            dados = []
            
            for row in worksheet.iter_rows(min_row=2, values_only=True):
                if row[0] is not None:  # Ignora linhas vazias
                    dados.append(row)
            
            return dados
        except Exception as e:
            print(f"❌ Erro ao obter dados: {e}")
            return None
    
    def inserir_dados(self, nome_aba, dados):
        try:
            worksheet = self.workbook[nome_aba]
            ultima_linha = worksheet.max_row + 1
            
            for col_idx, valor in enumerate(dados, 1):
                worksheet.cell(row=ultima_linha, column=col_idx, value=valor)
            
            self.workbook.save(self.arquivo)
            print("✅ Dados inseridos com sucesso!")
            return True
        except Exception as e:
            print(f"❌ Erro ao inserir dados: {e}")
            return False
    
    def atualizar_dados(self, nome_aba, linha, dados):
        try:
            worksheet = self.workbook[nome_aba]
            
            for col_idx, valor in enumerate(dados, 1):
                worksheet.cell(row=linha, column=col_idx, value=valor)
            
            self.workbook.save(self.arquivo)
            print("✅ Dados atualizados com sucesso!")
            return True
        except Exception as e:
            print(f"❌ Erro ao atualizar dados: {e}")
            return False
    
    def exportar_relatorio(self, nome_arquivo, dados_relatorio):
        try:
            novo_workbook = openpyxl.Workbook()
            worksheet = novo_workbook.active
            worksheet.title = "Relatório"
            
            # Cabeçalho
            cabecalho = list(dados_relatorio[0].keys())
            for col_idx, titulo in enumerate(cabecalho, 1):
                worksheet.cell(row=1, column=col_idx, value=titulo)
            
            # Dados
            for row_idx, registro in enumerate(dados_relatorio, 2):
                for col_idx, valor in enumerate(registro.values(), 1):
                    worksheet.cell(row=row_idx, column=col_idx, value=valor)
            
            novo_workbook.save(nome_arquivo)
            print(f"✅ Relatório exportado para {nome_arquivo} com sucesso!")
            return True
        except Exception as e:
            print(f"❌ Erro ao exportar relatório: {e}")
            return False
    
    def desconectar(self):
        if self.workbook:
            self.workbook.close()
            print("✅ Desconectado do arquivo Excel.")
```

</details>

### Geração de Relatórios e Exportação de Dados

Implementei funcionalidades para gerar relatórios consolidados em diferentes formatos:
- Relatórios por turma com listagem de alunos, grupos e scores
- Cálculo e exibição do Fator de Ensino Evolutivo (FEE) por aluno e turma
- Exportação de dados consolidados para Excel, permitindo análise posterior em ferramentas externas
- Relatórios de feedback dos professores com consolidação de avaliações

<details>
  <summary>📝 Exemplo: Geração de Relatório</summary>

```python
class RelatorioService:
    def __init__(self, excel_manager):
        self.excel_manager = excel_manager
    
    def gerar_relatorio_turma(self, turma_id):
        # Obter dados da turma
        alunos = self.excel_manager.obter_dados('Alunos')
        scores = self.excel_manager.obter_dados('Scores')
        
        print("\n" + "="*70)
        print("RELATÓRIO DE TURMA")
        print("="*70)
        
        for aluno in alunos:
            if aluno[2] == turma_id:  # Filtra por turma
                media_scores = self._calcular_media_scores(aluno[0], scores)
                fee = self.calcular_fee(media_scores)
                
                print(f"Aluno: {aluno[1]}")
                print(f"Grupo: {aluno[3] or 'Não atribuído'}")
                print(f"Média de Scores: {media_scores:.2f}")
                print(f"FEE (Fator de Ensino Evolutivo): {fee:.2f}")
                print("-" * 70)
    
    def calcular_fee(self, media_scores):
        # Cálculo do FEE baseado em média ponderada
        return (media_scores * 10) / 100 if media_scores > 0 else 0
    
    def _calcular_media_scores(self, aluno_id, scores):
        total = 0
        contador = 0
        
        for score in scores:
            if score[0] == aluno_id:
                total += score[2]
                contador += 1
        
        return total / contador if contador > 0 else 0
    
    def exportar_relatorio_excel(self, turma_id, nome_arquivo):
        alunos = self.excel_manager.obter_dados('Alunos')
        scores = self.excel_manager.obter_dados('Scores')
        
        dados_relatorio = []
        
        for aluno in alunos:
            if aluno[2] == turma_id:
                media = self._calcular_media_scores(aluno[0], scores)
                fee = self.calcular_fee(media)
                
                dados_relatorio.append({
                    'ID': aluno[0],
                    'Nome': aluno[1],
                    'Grupo': aluno[3] or 'N/A',
                    'Média de Scores': f"{media:.2f}",
                    'FEE': f"{fee:.2f}"
                })
        
        self.excel_manager.exportar_relatorio(nome_arquivo, dados_relatorio)
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

### Manipulação de Dados com Excel

Trabalhar com arquivos Excel através de Python me ensinou:
- Leitura e escrita de arquivos .xlsx
- Navegação entre abas e células
- Validação de dados em planilhas
- Exportação e importação de dados em massa
- Tratamento de erros na manipulação de arquivos

### Desenvolvimento de Interface CLI

Desenvolver uma interface de linha de comando intuitiva e responsiva me preparou para criar aplicações backend robustas. Aprendi a importância de feedback claro ao usuário, validação de entrada e navegação lógica.

### Projeto e Arquitetura de Software

Participei da arquitetura de um sistema com múltiplas camadas (lógica, acesso a dados, interface), aprendendo princípios de separação de responsabilidades, modularidade e reutilização de código.

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
| Microsoft Excel | ⭐⭐⭐⭐☆ | Sei fazer com ajuda |
| Manipulação de Arquivos Excel (.xlsx) | ⭐⭐⭐⭐⭐ | Sei fazer com autonomia |
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
| **Resolução de Problemas Complexos** | Implementei soluções para requisitos educacionais específicos (cálculo de FEE, gerenciamento de ciclos) e integração com dados em Excel. |
| **Pensamento Lógico** | Estruturei a lógica de negócio de forma clara e modular, facilitando manutenção e extensão do sistema. |
| **Comunicação Técnica** | Participei de reuniões de sprint, explicando implementações técnicas e recebendo feedback de stakeholders. |
| **Trabalho em Equipe** | Colaborei com outros desenvolvedores na integração de código e resolução de conflitos no Git. |
| **Adaptabilidade** | Aprendi Python, manipulação de Excel e conceitos de metodologia Scrum durante o projeto. |
| **Atenção a Detalhes** | Implementei validações rigorosas para garantir integridade de dados no sistema. |
| **Gestão de Tempo** | Organizei tarefas dentro das sprints para cumprir prazos e entregar incrementos funcionais. |

---

## Como Contribui para o Projeto 🔧

Minha contribuição foi distribuída entre as quatro sprints:

**Sprint 1**: Implementação da estrutura base do projeto, criação de classes para alunos e professores, desenvolvimento da interface de menu inicial e integração básica com arquivos Excel.

**Sprint 2**: Desenvolvimento de funcionalidades de gerenciamento de turmas e grupos, implementação de validações de dados e refatoração do código para melhor modularidade.

**Sprint 3**: Implementação da lógica de atribuição de scores e feedbacks, desenvolvimento de relatórios de alunos e cálculo de estatísticas descritivas.

**Sprint 4**: Consolidação do menu principal, implementação de exportação de dados em Excel, testes finais e documentação do código.

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
    <td><a href="https://github.com/Porygon-Users/API-Porygon/tree/main">Sistema de Gerenciamento Acadêmico PBLTeX - Python + CLI</a></td>
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
