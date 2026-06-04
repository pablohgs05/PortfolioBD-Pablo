# API 5º Semestre - Dashboard de Inteligência de Negócios para Gestão de Projetos - Neo Horizon

<div align="center">
  <a href="https://github.com/FatecNeoHorizon/API_5S">
    <img src="https://img.shields.io/badge/GitHub-Repositório Projeto-181717?style=for-the-badge&logo=github" alt="Repositório">
  </a>
</div>

## Tema do Projeto 📋

**Dashboard de Inteligência de Negócios para Gestão de Projetos - Neo Horizon**

O projeto consiste em uma aplicação web de inteligência de negócios desenvolvida para a Necto, empresa de desenvolvimento de softwares, com o objetivo de aprimorar a gestão de projetos atualmente realizada na plataforma Jira. A solução fornece um painel de controle centralizado que transforma dados brutos em informações estratégicas, permitindo visibilidade sobre indicadores críticos, acompanhamento de progresso, controle detalhado de acesso por perfil de usuário e tomada de decisões assertivas através de dashboards intuitivos e relatórios consolidados.

## Cliente

**Necto** - Empresa de desenvolvimento de softwares focada em soluções estratégicas e gestão ágil de projetos

## Tecnologias Adotadas 💻

<div align="center">
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" width="100" height="100" alt="JavaScript"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/vuejs/vuejs-original-wordmark.svg" width="100" height="100" alt="Vue.js"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original-wordmark.svg" width="100" height="100" alt="Java"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/spring/spring-original-wordmark.svg" width="100" height="100" alt="Spring Boot"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original-wordmark.svg" width="100" height="100" alt="MySQL"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/docker/docker-original-wordmark.svg" width="100" height="100" alt="Docker"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/git/git-original-wordmark.svg" width="100" height="100" alt="Git"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/figma/figma-original.svg" width="100" height="100" alt="Figma"/>
</div>

### Descrição das Tecnologias

- **[Vue.js 3](https://vuejs.org/)**: Framework JavaScript progressivo utilizado para desenvolvimento do frontend, permitindo a construção de interfaces dinâmicas, responsivas e altamente interativas para visualização de dashboards, filtros avançados e componentes reutilizáveis. Vue.js foi escolhido pela sua curva de aprendizado suave, eficiência no desenvolvimento ágil e excelente suporte a reatividade de dados.

- **[JavaScript ES6+](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript)**: Linguagem de programação utilizada para implementar toda a lógica de interação no cliente, manipulação do DOM, gestão de estado e comunicação assíncrona com a API backend através de requisições AJAX/Fetch.

- **[Vuetify](https://vuetifyjs.com/)**: Biblioteca de componentes UI para Vue.js que segue o padrão Material Design, fornecendo componentes pré-estilizados e acessíveis para construção rápida de interfaces profissionais com tabelas, gráficos, modais e formulários responsivos.

- **[Chart.js / ApexCharts](https://www.chartjs.org/)**: Bibliotecas de visualização de dados utilizadas para renderizar gráficos e dashboards interativos, permitindo a apresentação clara de métricas de desempenho, custos, ciclo de tempo e distribuição de carga de trabalho em diferentes formatos (gráficos de barras, pizza, linha, etc).

- **[Axios](https://axios-http.com/)**: Cliente HTTP baseado em Promise utilizado para realizar requisições assíncronas à API backend, gerenciando headers, autenticação via tokens JWT e tratamento de erros de forma centralizada.

- **[Java 22](https://www.java.com/pt-BR/)**: Linguagem de programação utilizada no desenvolvimento do backend, fornecendo APIs REST robustas que alimentam o frontend com dados consolidados e processados.

- **[Spring Boot 3.3.3](https://spring.io/projects/spring-boot)**: Framework para desenvolvimento ágil da API REST backend, com suporte a Spring Data JPA para persistência de dados, Spring Security para autenticação/autorização e integração com APIs externas do Jira.

- **[MySQL](https://www.mysql.com/)**: Sistema de gerenciamento de banco de dados relacional utilizado para armazenar dados estruturados dos projetos, usuários, métricas, histórico de movimentações de cards e permitir consultas otimizadas para geração de relatórios.

- **[Docker](https://www.docker.com/)**: Plataforma de containerização que permite empacotar tanto frontend quanto backend em containers isolados, facilitando deployment consistente em diferentes ambientes (desenvolvimento, teste e produção).

- **[Git](https://git-scm.com/)**: Sistema de controle de versão distribuído utilizado para gerenciar todo o código-fonte do projeto, facilitando colaboração entre desenvolvedores, rastreamento de mudanças e implementação de CI/CD.

- **[Figma](https://www.figma.com/)**: Ferramenta de design colaborativo utilizada para prototipação das interfaces de usuário, criação de componentes reutilizáveis e definição de padrão visual antes da implementação no frontend.

---

## Arquitetura e Estrutura do Projeto 🏗️

### Separação entre Client e Server

Este projeto adota o padrão de **separação explícita entre frontend (client) e backend (server)** em repositórios independentes, permitindo:
- Desenvolvimento paralelo de equipes especializadas
- Escalabilidade e independência de deployment
- Comunicação clara através de APIs RESTful bem documentadas
- Facilidade na manutenção e evolução de cada camada isoladamente

### Requisitos Funcionais

| ID | Requisito | Descrição |
|:---|:---|:---|
| **NH-RF-001** | *Painel de Carga de Trabalho Individual* | Visualizar cards atribuídos ao usuário logado, agrupados por projeto, com quantidade de cards em cada status |
| **NH-RF-002** | *Relatório de Desempenho do Time* | Líder de Equipe visualiza carga de trabalho da equipe com filtros por projeto |
| **NH-RF-003** | *Painel de Visão Geral do Projeto e Custos* | Gerente visualiza quantidade de cards por status, tempo médio de ciclo e custos do projeto |
| **NH-RF-004** | *Relatório de Atividades por Período* | Relatório consolidado de cards criados, movidos ou concluídos com quebra por período, desenvolvedor e projeto |
| **NH-RF-005** | *Identificação de Bugs e Retrabalhos* | Sistema identifica e contabiliza bugs por projeto e por desenvolvedor |
| **NH-RF-006** | *Sistema de Controle de Acesso* | Três níveis de permissão (Membro, Líder, Gerente) com visualização restrita de dados |
| **NH-RF-007** | *Relatório de Horas por Módulo* | Relatório de horas registradas em Épico, Produto e Entregável |

### Requisitos Não-Funcionais

| ID | Requisito | Descrição |
|:---|:---|:---|
| **NH-RNF-001** | *Documentação Técnica* | API documentada com Swagger, incluindo endpoints, métodos e parâmetros |
| **NH-RNF-002** | *Usabilidade* | Interface intuitiva e limpa para todos os perfis de usuário |
| **NH-RNF-003** | *Modelagem de Banco de Dados* | Banco de dados relacional otimizado com integridade referencial e índices |

### Cronograma de Desenvolvimento

- **Sprint 1** (08/09 - 28/09): Implementação de dashboards iniciais, estrutura de componentes Vue e integração básica com backend
- **Sprint 2** (06/10 - 26/10): Desenvolvimento de relatórios detalhados, sistema de filtros avançados e refatoração de layouts
- **Sprint 3** (03/11 - 23/11): Melhorias de UX, otimização de performance, autenticação visual e documentação de padrões DevOps

---

## Contribuições Individuais 🎯

### Desenvolvimento Frontend com Vue.js

Como desenvolvedor frontend principal, fui responsável pela implementação de toda a interface de usuário do sistema de dashboards utilizando Vue.js 3. Meu foco foi criar componentes reutilizáveis, dinâmicos e altamente responsivos que permitissem aos usuários visualizar, filtrar e interagir com dados complexos de forma intuitiva.

Implementei a arquitetura de componentes seguindo o padrão de decomposição em unidades reutilizáveis e bem encapsuladas. Cada componente possui sua própria lógica de estado (data), métodos de interação (methods), computed properties para reatividade eficiente e watchers para monitorar mudanças críticas. Desenvolvi componentes específicos para:

- **Dashboards de Métricas**: Painéis que agregam e exibem indicadores-chave de performance (KPIs) com cards informativos, números destacados e tendências
- **Gráficos Interativos**: Visualizações usando Chart.js e ApexCharts para representar dados de forma clara (gráficos de barras para carga de trabalho, gráficos de linha para evolução temporal, gráficos de pizza para distribuição de status)
- **Tabelas Dinâmicas**: Componentes de tabela com paginação, sorting, filtros inline e ações contextuais para manipulação de dados
- **Filtros Avançados**: Sistema modular de filtros que permite refinar dados por projeto, período, desenvolvedor, tipo de card e status

### Gestão de Estado e Comunicação com Backend

Implementei um sistema robusto de gestão de estado utilizando Vue 3 Composition API e Pinia (ou Vuex, conforme a arquitetura adotada), centralizado em stores que gerenciam:
- Estado global de autenticação e dados do usuário logado
- Cache de dados de dashboards para otimizar requisições
- Histórico de filtros aplicados
- Notificações e alertas para feedback ao usuário

Desenvolvi a camada de serviços que abstrai as chamadas HTTP para a API backend, utilizando Axios com interceptadores para:
- Injeção automática de tokens JWT nas requisições autenticadas
- Tratamento centralizado de erros e redirecionamento para login quando necessário
- Retry automático para requisições que falharem temporariamente
- Logging de requisições para debugging em produção

<details>
  <summary>📝 Exemplo: Componente de Dashboard com Gráfico Interativo</summary>

```vue
<template>
  <div class="dashboard-container">
    <div class="header">
      <h1>Painel de Desempenho do Projeto</h1>
      <div class="filters">
        <select v-model="selectedProject" @change="atualizarDados">
          <option value="">Selecione um projeto</option>
          <option v-for="projeto in projetos" :key="projeto.id" :value="projeto.id">
            {{ projeto.nome }}
          </option>
        </select>
        <date-range-picker v-model="dateRange" @change="atualizarDados" />
      </div>
    </div>

    <div class="metrics-grid">
      <!-- Cards de Métricas Principais -->
      <metric-card 
        title="Total de Cards" 
        :value="totalCards" 
        icon="layers"
        color="primary"
      />
      <metric-card 
        title="Cards em Andamento" 
        :value="cardsEmAndamento" 
        icon="play_circle"
        color="warning"
      />
      <metric-card 
        title="Cards Concluídos" 
        :value="cardsConcluidos" 
        icon="check_circle"
        color="success"
      />
      <metric-card 
        title="Tempo Médio de Ciclo (dias)" 
        :value="tempoMedioCiclo" 
        icon="timer"
        color="info"
      />
    </div>

    <div class="charts-grid">
      <!-- Gráfico de Distribuição de Status -->
      <div class="chart-container">
        <h3>Distribuição de Cards por Status</h3>
        <canvas ref="statusChart"></canvas>
      </div>

      <!-- Gráfico de Velocidade do Time -->
      <div class="chart-container">
        <h3>Velocidade de Conclusão (últimas 4 sprints)</h3>
        <canvas ref="velocidadeChart"></canvas>
      </div>

      <!-- Gráfico de Distribuição de Carga de Trabalho -->
      <div class="chart-container" style="grid-column: 1 / -1;">
        <h3>Carga de Trabalho por Desenvolvedor</h3>
        <canvas ref="cargaTrabalhoChart"></canvas>
      </div>
    </div>

    <!-- Tabela Detalhada de Cards -->
    <div class="cards-table">
      <h3>Cards por Status</h3>
      <data-table 
        :items="cardsDetalhados"
        :columns="colunasTabela"
        :loading="carregando"
        @click:row="abrirDetalhesCard"
      />
    </div>
  </div>
</template>

<script>
import { ref, computed, onMounted } from 'vue';
import { useStore } from 'pinia';
import { projetoService } from '@/services/projetoService';
import { dashboardService } from '@/services/dashboardService';
import Chart from 'chart.js/auto';
import MetricCard from '@/components/MetricCard.vue';
import DataTable from '@/components/DataTable.vue';
import DateRangePicker from '@/components/DateRangePicker.vue';

export default {
  name: 'DashboardProjeto',
  components: {
    MetricCard,
    DataTable,
    DateRangePicker
  },
  setup() {
    const store = useStore();
    const selectedProject = ref('');
    const dateRange = ref({ start: null, end: null });
    const carregando = ref(false);
    const projetos = ref([]);
    const dados = ref(null);
    
    const statusChart = ref(null);
    const velocidadeChart = ref(null);
    const cargaTrabalhoChart = ref(null);
    
    let chartInstances = {
      status: null,
      velocidade: null,
      cargaTrabalho: null
    };

    const totalCards = computed(() => dados.value?.totalCards || 0);
    const cardsEmAndamento = computed(() => dados.value?.cardsEmAndamento || 0);
    const cardsConcluidos = computed(() => dados.value?.cardsConcluidos || 0);
    const tempoMedioCiclo = computed(() => (dados.value?.tempoMedioCiclo || 0).toFixed(2));
    const cardsDetalhados = computed(() => dados.value?.cards || []);

    const colunasTabela = [
      { key: 'titulo', label: 'Título' },
      { key: 'status', label: 'Status' },
      { key: 'desenvolvedor', label: 'Desenvolvedor' },
      { key: 'dataVencimento', label: 'Vencimento' },
      { key: 'prioridade', label: 'Prioridade' }
    ];

    const atualizarDados = async () => {
      carregando.value = true;
      try {
        const filtros = {
          projetoId: selectedProject.value,
          dataInicio: dateRange.value.start,
          dataFim: dateRange.value.end
        };
        
        dados.value = await dashboardService.obterDashboardProjeto(filtros);
        
        // Atualizar gráficos após dados carregados
        atualizarGraficos();
      } catch (erro) {
        console.error('Erro ao carregar dashboard:', erro);
        store.dispatch('adicionarNotificacao', {
          tipo: 'erro',
          mensagem: 'Erro ao carregar dados do dashboard'
        });
      } finally {
        carregando.value = false;
      }
    };

    const atualizarGraficos = () => {
      // Destruir instâncias anteriores
      if (chartInstances.status) chartInstances.status.destroy();
      if (chartInstances.velocidade) chartInstances.velocidade.destroy();
      if (chartInstances.cargaTrabalho) chartInstances.cargaTrabalho.destroy();

      // Gráfico de Status
      chartInstances.status = new Chart(statusChart.value, {
        type: 'doughnut',
        data: {
          labels: dados.value.statusLabels,
          datasets: [{
            data: dados.value.statusValues,
            backgroundColor: ['#4CAF50', '#FFC107', '#F44336', '#2196F3'],
            borderColor: '#fff',
            borderWidth: 2
          }]
        },
        options: {
          responsive: true,
          plugins: {
            legend: { position: 'bottom' }
          }
        }
      });

      // Gráfico de Velocidade
      chartInstances.velocidade = new Chart(velocidadeChart.value, {
        type: 'bar',
        data: {
          labels: dados.value.sprintLabels,
          datasets: [{
            label: 'Cards Concluídos',
            data: dados.value.velocidadeValues,
            backgroundColor: '#2196F3',
            borderRadius: 5
          }]
        },
        options: {
          responsive: true,
          scales: {
            y: { beginAtZero: true }
          }
        }
      });

      // Gráfico de Carga de Trabalho
      chartInstances.cargaTrabalho = new Chart(cargaTrabalhoChart.value, {
        type: 'bar',
        data: {
          labels: dados.value.desenvolvedores,
          datasets: [{
            label: 'Horas Alocadas',
            data: dados.value.horasAlocadas,
            backgroundColor: '#FF9800',
            borderRadius: 5
          }]
        },
        options: {
          indexAxis: 'y',
          responsive: true,
          scales: {
            x: { beginAtZero: true }
          }
        }
      });
    };

    const abrirDetalhesCard = (card) => {
      store.dispatch('abrirModalDetalhesCard', card);
    };

    onMounted(async () => {
      projetos.value = await projetoService.listarProjetosPorUsuario(store.state.usuarioId);
      if (projetos.value.length > 0) {
        selectedProject.value = projetos.value[0].id;
        await atualizarDados();
      }
    });

    return {
      selectedProject,
      dateRange,
      projetos,
      carregando,
      totalCards,
      cardsEmAndamento,
      cardsConcluidos,
      tempoMedioCiclo,
      cardsDetalhados,
      colunasTabela,
      statusChart,
      velocidadeChart,
      cargaTrabalhoChart,
      atualizarDados,
      abrirDetalhesCard
    };
  }
};
</script>

<style scoped>
.dashboard-container {
  padding: 2rem;
  background: #f5f5f5;
  min-height: 100vh;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 2rem;
}

.header h1 {
  font-size: 2rem;
  color: #333;
}

.filters {
  display: flex;
  gap: 1rem;
}

.filters select,
.filters input {
  padding: 0.5rem;
  border: 1px solid #ddd;
  border-radius: 4px;
  font-size: 1rem;
}

.metrics-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1.5rem;
  margin-bottom: 2rem;
}

.charts-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
  gap: 1.5rem;
  margin-bottom: 2rem;
}

.chart-container {
  background: white;
  padding: 1.5rem;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

.chart-container h3 {
  margin-top: 0;
  color: #333;
  font-size: 1.1rem;
}

.cards-table {
  background: white;
  padding: 1.5rem;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

.cards-table h3 {
  margin-top: 0;
  color: #333;
}
</style>
```

</details>

### Implementação de Componentes UI com Vuetify

Utilizei a biblioteca Vuetify para construir rapidamente uma interface profissional e consistente. Implementei:

- **Cards de Métricas**: Componentes que exibem indicadores principais com ícones, valores destacados e cores temáticas
- **Data Grids**: Tabelas avançadas com suporte a paginação, busca, ordenação e ações em lote
- **Modais e Diálogos**: Componentes para confirmações, edições e detalhes de cards
- **Formulários Responsivos**: Campos de entrada, seletores de data, checkboxes e multiselects para filtros avançados
- **Navegação e Menu**: Sidebars, toolbars e breadcrumbs para navegação intuitiva entre seções

### Otimização de Performance e UX

Implementei diversas estratégias para otimizar a performance e experiência do usuário:

- **Code Splitting**: Divisão de código em chunks para carregamento mais rápido de componentes menos utilizados
- **Lazy Loading**: Carregamento sob demanda de componentes e dados para reduzir o tamanho inicial do bundle
- **Caching Inteligente**: Cache de dados em memória (Pinia) para evitar requisições desnecessárias
- **Paginação e Virtualização**: Implementação de virtual scrolling em listas grandes para renderização eficiente
- **Indicadores de Carregamento**: Skeletons, spinners e progress bars para melhor feedback ao usuário

<details>
  <summary>📝 Exemplo: Serviço de Requisições HTTP com Interceptadores</summary>

```javascript
import axios from 'axios';
import { useStore } from 'pinia';

const api = axios.create({
  baseURL: process.env.VUE_APP_API_URL || 'http://localhost:8080/api',
  timeout: 10000,
  headers: {
    'Content-Type': 'application/json'
  }
});

// Interceptador de Requisição
api.interceptors.request.use(
  (config) => {
    const store = useStore();
    const token = store.state.auth.token;
    
    if (token) {
      config.headers.Authorization = `Bearer ${token}`;
    }
    
    // Log de requisição em desenvolvimento
    if (process.env.NODE_ENV === 'development') {
      console.log(`[API] ${config.method.toUpperCase()} ${config.url}`, config.data);
    }
    
    return config;
  },
  (error) => Promise.reject(error)
);

// Interceptador de Resposta
api.interceptors.response.use(
  (response) => {
    if (process.env.NODE_ENV === 'development') {
      console.log(`[API Response] ${response.status}`, response.data);
    }
    return response.data;
  },
  (error) => {
    const store = useStore();
    
    if (error.response?.status === 401) {
      // Token expirado ou inválido
      store.dispatch('logout');
      window.location.href = '/login';
    } else if (error.response?.status === 403) {
      // Acesso negado
      store.dispatch('adicionarNotificacao', {
        tipo: 'erro',
        mensagem: 'Você não tem permissão para acessar este recurso'
      });
    } else if (error.response?.status >= 500) {
      // Erro do servidor
      store.dispatch('adicionarNotificacao', {
        tipo: 'erro',
        mensagem: 'Erro no servidor. Tente novamente mais tarde.'
      });
    }
    
    return Promise.reject(error);
  }
);

export default api;
```

</details>

### Responsividade e Acessibilidade

Implementei a interface seguindo os princípios de mobile-first responsiveness, garantindo que o dashboard funcione perfeitamente em:
- Desktop (1920px e acima)
- Tablets (768px a 1024px)
- Smartphones (até 768px)

Utilizei media queries e componentes flexíveis do Vuetify para adaptar layouts e espaçamentos conforme o tamanho da tela. Além disso, implementei:

- **Acessibilidade WCAG 2.1**: Atributos ARIA, labels semânticos, contraste adequado de cores
- **Teclado Navigation**: Suporte completo para navegação e interação via teclado
- **Screen Reader Friendly**: Estrutura semântica e descrições adequadas para leitores de tela

---

## Padrões de Desenvolvimento Aplicados 🛠️

Durante o projeto, nossa equipe manteve rigorosos padrões de desenvolvimento documentados na Wiki do projeto:

### Commits Padronizados
Seguimos o padrão **Conventional Commits**, garantindo mensagens claras e rastreáveis:
```
feat(#15): Adiciona dashboard de desempenho do time
- Implementa visualização de carga de trabalho
- Adiciona filtros por projeto e período
- Integra gráficos de velocidade
```

### Code Review e Qualidade
- Todos os Pull Requests passaram por revisão obrigatória
- Checklist de conformidade com padrões de código
- Testes unitários e integração contínua via GitHub Actions
- Análise de qualidade com SonarQube para identificar code smells e vulnerabilidades

### DevOps e Integração Contínua
Nosso pipeline de CI/CD implementa:
- **Build Automático**: Compilação e bundling do frontend a cada push
- **Testes Automatizados**: Suite de testes unitários e E2E executados automaticamente
- **Deploy Contínuo**: Publicação automática para ambientes de staging e produção
- **Containerização Docker**: Empacotamento da aplicação em containers para deployment consistente

---

---

## Aprendizados Efetivos 📚

Este projeto foi fundamental para consolidar minha compreensão de desenvolvimento frontend moderno em larga escala:

### Arquitetura de Componentes Vue em Escala

Aprendi a estruturar aplicações Vue.js complexas com múltiplos dashboards mantendo componentes bem desacoplados, reutilizáveis e testáveis. A decomposição cuidadosa em componentes menores facilitou a manutenção e permitiu que múltiplos membros da equipe trabalhassem em paralelo sem conflitos.

### Gestão de Estado Avançada

Implementei um sistema robusto de state management utilizando Pinia, gerenciando complexos fluxos de dados como autenticação, caching, notificações e histórico de filtros. Compreendi deeply os benefícios de centralizar a lógica de estado e como isso facilita debug e testes.

### Performance em Aplicações Pesadas de Dados

Trabalhei com técnicas avançadas de otimização incluindo lazy loading, code splitting, virtual scrolling e caching inteligente. Compreendi como cada decisão de design impacta diretamente na experiência do usuário com dashboards de grande volume de dados.

### Integração API e Tratamento de Erros

Desenvolvi uma camada de serviços robusta que abstrai as chamadas HTTP com tratamento centralizado de erros, retry automático, interceptadores de autenticação e logging. Aprendi a importância de uma camada de abstração bem desenhada.

### Responsividade e Acessibilidade

Implementei dashboards que funcionam perfeitamente em desktop, tablets e smartphones, além de garantir conformidade com padrões WCAG 2.1 para acessibilidade. Apreciéi como esses requisitos não são "extras" mas parte integral de uma aplicação profissional.

### Trabalho em Equipe Ágil e DevOps

Participei de um ciclo completo de Scrum com standups diários, planejamento, retrospectivas e refinamento contínuo. Compreendi como padrões bem definidos (commits, PRs, CI/CD) facilitam a colaboração em equipes de múltiplos desenvolvedores.

---

## Competências Desenvolvidas 🏆

### Hard Skills

| Tecnologia/Metodologia | Proficiência | Classificação |
|------------------------|--------------|---------------|
| Vue.js 3 | ⭐⭐⭐⭐⭐ | Sei fazer com autonomia |
| JavaScript ES6+ | ⭐⭐⭐⭐⭐ | Sei fazer com autonomia |
| Vuetify (Material Design) | ⭐⭐⭐⭐☆ | Sei fazer com ajuda |
| Chart.js / ApexCharts | ⭐⭐⭐⭐☆ | Sei fazer com ajuda |
| Axios / Requisições HTTP | ⭐⭐⭐⭐⭐ | Sei fazer com autonomia |
| Pinia (State Management) | ⭐⭐⭐⭐☆ | Sei fazer com ajuda |
| Composition API (Vue 3) | ⭐⭐⭐⭐⭐ | Sei fazer com autonomia |
| Responsividade / Mobile-First | ⭐⭐⭐⭐⭐ | Sei fazer com autonomia |
| Git/Versionamento | ⭐⭐⭐⭐⭐ | Sei fazer com autonomia |
| Docker / Containerização | ⭐⭐⭐⭐☆ | Sei fazer com ajuda |

### Soft Skills

| Habilidade | Descrição |
|-----------|-----------|
| **Resolução de Problemas Complexos** | Implementei soluções sofisticadas para renderizar e interagir com grandes volumes de dados em tempo real sem comprometer performance. |
| **Pensamento Crítico** | Analisei requisitos de negócio e sugeri arquiteturas de frontend escaláveis e mantíveis de longo prazo. |
| **Comunicação Técnica** | Participei ativamente de daily standups, code reviews e retrospectivas, articulando desafios técnicos de forma clara. |
| **Trabalho em Equipe** | Colaborei com backend team através de APIs bem definidas, realizei code reviews construtivos e mentorei desenvolvedores juniores. |
| **Adaptabilidade** | Aprendi Composition API, Pinia, Vuetify e bibliotecas de gráficos durante o projeto, adaptando-me rapidamente a novos padrões. |
| **Atenção a Detalhes** | Validei acessibilidade, responsividade, performance e user experience de forma rigorosa. |
| **Gestão de Tempo** | Organizei sprints de 2-3 semanas, priorizando features de valor alto e mantendo cadência de delivery. |

---

## Como Contribui para o Projeto 🔧

Minha contribuição foi distribuída entre as três sprints:

**Sprint 1** (08/09 - 28/09): Arquitetura inicial da aplicação Vue.js, setup de componentes base (layout, navbar, sidebar), integração com backend em desenvolvimento e criação de dashboards iniciais de métricas de alto nível.

**Sprint 2** (06/10 - 26/10): Implementação de relatórios detalhados com gráficos interativos, sistema modular de filtros avançados, otimizações de performance com lazy loading e refatoração de layouts para responsividade total.

**Sprint 3** (03/11 - 23/11): Melhorias finais de UX/UI, implementação de estado global robusto, testes E2E, documentação de componentes e suporte ao DevOps (containerização Docker do frontend).

---

## Reflexão Final 💭

Este projeto consolidou meu entendimento de como construir aplicações frontend profissionais que realmente agregam valor a usuários reais. Através do "Dashboard de Inteligência de Negócios Neo Horizon", aprendi que qualidade em frontend vai muito além de "fazer funcionar":

- Arquitetura bem pensada que cresce com o projeto
- Performance é uma feature, não um detalhe
- Acessibilidade beneficia todos, não apenas pessoas com deficiências
- DevOps adequado permite que equipes trabalhem em paralelo sem chaos
- Comunicação clara com a equipe (através de commits, PRs, código legível) é tão importante quanto o código em si

Estou preparado para construir aplicações frontend ainda mais complexas e impactantes, aplicando todos esses princípios em contextos ainda mais desafiadores.

---

<div align="center">

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
    <td><a href="https://github.com/pablohgs05/PortfolioBD-Pablo/blob/main/API_5.md">Dashboard de Inteligência de Negócios para Gestão de Projetos - Neo Horizon</a></td>
  </tr>
  <tr>
    <td>6º Semestre:</td>
    <td><a href="https://github.com/pablohgs05/PortfolioBD-Pablo/blob/main/API_6.md">API 6</a></td>
  </tr>
</table>

</div>

