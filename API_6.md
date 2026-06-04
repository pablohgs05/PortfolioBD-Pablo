# API 6º Semestre - Plataforma de Análise e Previsibilidade de Indicadores de Qualidade de Energia Elétrica - ATHOS

<div align="center">
  <a href="https://github.com/AthosFatecSjc">
    <img src="https://img.shields.io/badge/GitHub-AthosFatecSjc-181717?style=for-the-badge&logo=github" alt="Repositório">
  </a>
</div>

## Tema do Projeto 📋

**Plataforma de Análise e Previsibilidade de Indicadores de Qualidade de Energia Elétrica (HiATHOS)**

O projeto consiste em uma plataforma analítica web desenvolvida em colaboração com a TECSYS para centralizar, processar e analisar dados públicos regulatórios da ANEEL (Agência Nacional de Energia Elétrica), transformando informações fragmentadas em indicadores estruturados de confiabilidade e qualidade da rede elétrica. A solução automatiza a coleta periódica de dados de distribuidoras de energia, armazena em banco de dados estruturado, oferece visualização geográfica interativa através de mapas de calor (heatmap), e implementa inteligência artificial para previsibilidade de indicadores críticos como DEC (Duração Equivalente de Interrupção) e FEC (Frequência Equivalente de Interrupção). O sistema suporta gestão de usuários com controle de acesso por papéis, compliance LGPD, rastreabilidade de operações via logging centralizado, e arquitetura dual backend (Java REST + Python ETL/Forecasting) para separação de responsabilidades e escalabilidade.

## Cliente

**TECSYS** - Empresa especializada em soluções de análise de dados para o setor de energia elétrica, focada em inteligência regulatória e business intelligence para distribuidoras

## Tecnologias Adotadas 💻

<div align="center">
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/vuejs/vuejs-original-wordmark.svg" width="100" height="100" alt="Vue.js"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/typescript/typescript-original.svg" width="100" height="100" alt="TypeScript"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original-wordmark.svg" width="100" height="100" alt="Java"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/spring/spring-original-wordmark.svg" width="100" height="100" alt="Spring Boot"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original-wordmark.svg" width="100" height="100" alt="Python"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/postgresql/postgresql-original-wordmark.svg" width="100" height="100" alt="PostgreSQL"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mongodb/mongodb-original-wordmark.svg" width="100" height="100" alt="MongoDB"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/docker/docker-original-wordmark.svg" width="100" height="100" alt="Docker"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/git/git-original-wordmark.svg" width="100" height="100" alt="Git"/>
</div>

### Descrição das Tecnologias

- **[Vue.js 3](https://vuejs.org/)**: Framework JavaScript progressivo utilizado para desenvolvimento do frontend, permitindo construção de interfaces dinâmicas e reativas. No projeto, Vue.js foi essencial para criar páginas de visualização interativa (MapaCalor com filtros geo-temporais, PaginaPrevisao com gráficos Prophet), páginas administrativas (AdminUsuarios, AdminLogs), e dashboard centralizado com integração seamless via Composition API com TypeScript.

- **[TypeScript](https://www.typescriptlang.org/)**: Superset tipado de JavaScript utilizado em todo o frontend, fornecendo type safety e autocompletar robusto durante desenvolvimento. Implementou tipos customizados para estruturas complexas como Conjunto (dados geográficos), Criticidade (nivelamento de risco), FiltrosMapa (estado de filtros), e schemas de resposta da API, garantindo confiabilidade em aplicações com lógica sofisticada.

- **[Java 21 / Spring Boot 3.x](https://spring.io/projects/spring-boot)**: Framework para desenvolvimento ágil da API REST backend, fornecendo controladores REST robustos para autenticação (Spring Security com JWT), gestão de usuários com controle de papéis (Role-based Access Control), endpoints administrativos para manipulação de dados, integração com flyway para versionamento de banco de dados, e suporte a testes unitários/integração com JUnit e MockMvc.

- **[Python 3.11+](https://www.python.org/)**: Linguagem utilizada no backend especializado em processamento de dados e inteligência artificial. Python foi escolhido para implementar o pipeline ETL que consome APIs públicas da ANEEL, valida e normaliza dados, e executa transformações complexas de dados energéticos em agregações geográficas e temporais.

- **[Prophet (Facebook)](https://facebook.github.io/prophet/)**: Modelo de previsão de séries temporais baseado em decomposição aditiva implementado em Python, especialmente eficaz em dados com sazonalidade forte (padrões energia elétrica por mês/estação). O modelo gera previsões de DEC e FEC com intervalos de confiança, permitindo que analistas antecipem regiões com risco elevado de interrupções.

- **[PostgreSQL 15+](https://www.postgresql.org/)**: Sistema de gerenciamento de banco de dados relacional utilizado para armazenar dados estruturados da aplicação: tabelas de usuários com status (PENDING/ACTIVE/REJECTED), termos e consentimentos versionados, logs de operações para auditoria, e especialmente o schema ANEEL com tabelas Lim, Sub, Dist, Perdas, Conj, SigIndicador, e Metrics para armazenar indicadores coletados com traçabilidade geográfica e temporal.

- **[MongoDB](https://www.mongodb.com/)**: Banco de dados NoSQL utilizado para armazenar logs de aplicação em formato semi-estruturado, permitindo flexibilidade em schemas de eventos e consultas complexas sem schema rígido. Complementa PostgreSQL para casos de uso que requerem escalabilidade horizontal em logs.

- **[Leaflet.js](https://leafletjs.com/)**: Biblioteca JavaScript de código aberto para mapas interativos utilizada na página MapaCalor, fornecendo visualização GeoJSON de municípios e conjuntos de consumidores com layer de heatmap colorido mostrando criticidade de DEC/FEC por região geográfica, suportando pan, zoom, e seleção de features.

- **[Axios](https://axios-http.com/)**: Cliente HTTP utilizado em todos os serviços TypeScript (mapaService, previsaoService, authService, etc.) para requisições à API backend, com interceptadores para injeção automática de JWT e tratamento centralizado de erros e respostas.

- **[Docker](https://www.docker.com/)**: Plataforma de containerização que empacota backend Java, backend Python, PostgreSQL, MongoDB, pgAdmin e outros serviços em containers isolados com docker-compose para orquestração, facilitando ambiente de desenvolvimento idêntico ao de produção e simplificando CI/CD.

- **[Git / Conventional Commits](https://www.conventionalcommits.org/)**: Sistema de controle de versão utilizado com padrão de commits estruturado (feat:, fix:, style:, refactor:) vinculados a tickets Jira (ATS-3, ATS-28, ATS-100, etc.), permitindo rastreamento claro de features e facilitação de geração automática de changelogs.

---

## Arquitetura e Estrutura do Projeto 🏗️

### Arquitetura Dual Backend

Este projeto adota uma arquitetura inovadora com **dois backends especializados** que se comunicam através de APIs RESTful e banco de dados compartilhado:

#### Backend Java (Spring Boot)
Responsável pela camada de apresentação, autenticação, autorização e operações do usuário:
- **Autenticação & Autorização**: Spring Security com JWT, controle de acesso baseado em papéis (ADMIN, USER)
- **Gestão de Usuários**: Endpoints CRUD para registro (ATS-3, ATS-7), aprovação/rejeição de usuários (ATS-104), edição de perfil (ATS-56), mudança de email com auditoria (ATS-113)
- **Conformidade LGPD**: Endpoints para direitos de sujeitos de dados, anonimização de registros pessoais (ATS-86), backup/restore com segurança de dados
- **Logging & Auditoria**: Sistema centralizado de logs (ATS-4, ATS-35, ATS-37) rastreando operações sensíveis de administrador e eventos de autenticação
- **Comunicação de Massa**: Endpoints para envio de emails em bulk para notificações de usuários (ATS-118)
- **Persistência**: Flyway para versionamento de schema, JPA para ORM

#### Backend Python (ETL Pipeline)
Responsável pela coleta, processamento e análise inteligente de dados:
- **Coleta de Dados ANEEL**: Jobs agendados que consomem APIs públicas de distribuidoras reguladas, validam estrutura de arquivos e normalizam dados (ATS-5, ATS-6)
- **Pipeline ETL**: Processamento com validação, transformação em agregações geográficas (por estado, distribuidor, conjunto de consumidores), e armazenamento idempotente (ATS-97)
- **Modelo de Previsibilidade Prophet**: Treinamento automático de modelos de séries temporais para DEC e FEC com histórico, geração de previsões com intervalos de confiança (ATS-15, ATS-123, ATS-124)
- **Jobs Agendados**: Cron jobs para execução periódica de coleta ANEEL e retreinamento de modelos
- **Testes Robustos**: Suite completa de testes unitários e integração para validar qualidade do pipeline

### Padrão Cliente-Servidor Distribuído

O projeto segue padrão explícito de separação com **dois repositórios Git independentes**:
- **Frontend (`frontend-develop`)**: Aplicação Vue.js 3 + TypeScript com Vite, componentes UI Material Design, roteador estruturado
- **Backend (`backend-develop`)**: Subpastas `backend-java/` e `backend-python/` com docker-compose orquestrando toda stack
- **Banco de Dados Compartilhado**: PostgreSQL como banco principal, MongoDB para logs (opcional)

Esta separação permite desenvolvimento paralelo, escalabilidade independente de cada camada, e evolução tecnológica desacoplada.

### Requisitos Funcionais

| ID | Requisito | Descrição |
|:---|:---|:---|
| **RF-01** | *Registro e Autenticação de Usuários* | Sistema permite auto-registro com email, senha, nome completo e telefone opcional; novo usuário criado com status PENDING; apenas usuários ACTIVE acessam plataforma; suporte a autenticação segura com JWT |
| **RF-02** | *Gestão Administrativa de Usuários* | Administradores visualizam, filtram, aprovam/rejeitam usuários com justificativa; editam perfis; granting/removal de privilégios admin; anonimização de dados pessoais quando solicitado |
| **RF-03** | *Termos, Consentimentos e Conformidade* | Sistema exibe Termos de Uso, Aviso de Privacidade, consentimento marketing opcional; registra versionamento de termos; mantém histórico de aceitações |
| **RF-04** | *Direitos de Sujeito de Dados (LGPD)* | Suporte a requisições de acesso, correção, anonimização ou exclusão de dados pessoais; auditoria de requisições |
| **RF-05** | *Logging e Auditoria Centralizada* | Sistema registra logs de autenticação, mudanças administrativas e eventos críticos com rastreabilidade completa; acesso restrito a admins; separação lógica de logs |
| **RF-06** | *Coleta Automática/Manual de Dados ANEEL* | Jobs agendados coletam periodicamente dados públicos ANEEL; admins podem executar coleta manual; suporte a múltiplas distribuidoras |
| **RF-07** | *Validação e Processamento de Dados* | Pipeline valida estrutura de arquivos coletados; normaliza dados; rejeita dados incompatíveis; armazena com traçabilidade de fonte e batch; previne duplicação |
| **RF-08** | *Preservação Histórica de Dados* | Sistema preserva histórico de dados válidos, versões de termos, registros de aceitos e eventos; garante consistência entre banco principal, logs e backups |
| **RF-09** | *Visualização Geográfica de Indicadores* | Sistema exibe heatmap interativo de indicadores DEC/FEC por município/região/distribuidor com Leaflet.js; filtra por ano, mês, estado, distribuidor, grupo de consumidores, subestação |
| **RF-10** | *Previsibilidade com IA (Prophet)* | Modelo Prophet traina automaticamente em histórico de DEC/FEC; gera previsões com intervalos de confiança; permite análise de tendências futuras |

### Requisitos Não-Funcionais

| ID | Requisito | Descrição |
|:---|:---|:---|
| **RNF-01** | *Segurança de Credenciais* | Senhas armazenadas apenas com hash criptográfico; credencial admin inicial não versionada em código; provisioning via mecanismo seguro |
| **RNF-02** | *Controle de Acesso* | Acesso restrito por papel (ADMIN, USER); dados pessoais e logs acessíveis apenas por admins; aplicação de need-to-know rules |
| **RNF-03** | *Conformidade LGPD* | Sistema adere a princípios de limitação de propósito, necessidade, adequação, segurança, transparência; coleta apenas dados estritamente necessários |
| **RNF-04** | *Integridade e Rastreabilidade* | Ações críticas rastreáveis; registros de usuários, termos, logs imutáveis sem sobrescrita indevida |
| **RNF-05** | *Proteção em Logs* | Senhas, tokens, secrets, cookies nunca registrados; masking de dados pessoais em logs |
| **RNF-06** | *Retenção e Disposal* | Logs retidos ~6 meses; backups ~90 dias; termos/consentimentos conforme política |
| **RNF-07** | *Disponibilidade Básica* | Sistema suporta volume inicial de usuários e coleta periódica sem degradação; suporta crescimento futuro |
| **RNF-08** | *Integrabilidade com Dados Públicos* | Pipeline consome APIs/arquivos públicos ANEEL de forma robusta; validação e tratamento de falhas em origem de dados |
| **RNF-09** | *Isolamento de Dados* | Dados analíticos geográficos públicos separados de dados pessoais; sem exposição de PII em visualizações |

### Cronograma de Desenvolvimento

**Timeline: 23 de Março - 31 de Maio de 2026 (3 meses, ~65 commits)**

- **Sprint 1 (23 Mar - 06 Abr)**: Fundação - Autenticação, Registro de Usuários, Login Screen, My Account endpoints (ATS-3, ATS-28, ATS-56)
- **Sprint 2 (07 Abr - 03 Mai)**: Core Features - Gestão de Usuários (ATS-104, ATS-103, ATS-113), Logs Administrativos (ATS-37, ATS-35), Compliance LGPD (ATS-86), Mapa de Calor com Leaflet (ATS-100), Filtros de Mês (ATS-115)
- **Sprint 3 (04 Mai - 31 Mai)**: IA & Refinamento - Gráficos de Previsão Prophet (ATS-124), Sanitização Pós-Backup (ATS-127), Email em Bulk (ATS-118), Modelo Treinado (ATS-123), Refinamentos finais

---

## Contribuições Individuais 🎯

### Desenvolvimento Full-Stack (Frontend Vue.js 3 + TypeScript)

Como desenvolvedor full-stack especialista em frontend, assumi responsabilidade principal na implementação da camada de apresentação utilizando Vue.js 3 com TypeScript e Vite. Minhas contribuições cobriram toda jornada do usuário na aplicação, desde autenticação até visualização avançada de dados geográficos com inteligência artificial.

**Autenticação & Onboarding** (ATS-28, ATS-27, ATS-3): Implementei tela de login responsiva com validação de credenciais, integração segura com JWT backend, fluxo de compartilhamento de consentimento (LoginSharingConsentPopup) para LGPD, e redirecionamento pós-login para dashboard apropriado. Também contribuí para registro de usuários (Cadastro.vue) com validação robusta de termos, tratamento de status PENDING e UX refinada com acessibilidade.

**Gestão de Usuários Administrativa** (ATS-103, ATS-104, ATS-113): Criei página completa AdminUsuarios.vue com tabela paginada avançada, filtros por nome/email/status, controles para aprovar/rejeitar/ativar/bloquear usuários com confirmações seguras, mudança de papéis (promover a ADMIN), edição de emails com auditoria centralizada. Implementei serviços Axios com interceptadores JWT, tratamento centralizado de erros 401/403/500, e retry automático em falhas temporárias.

**Visualização Geográfica com Mapa de Calor** (ATS-100, ATS-115): Desenvolvi componente MapaCalor.vue integrando Leaflet.js com GeoJSON de municípios brasileiros, renderizando heatmap interativo colorido baseado em criticidade de indicadores DEC/FEC. Implementei sistema robusto de filtros geo-temporais (ano, mês, distribuidor, estado, conjunto de consumidores, subestação) com recarregamento dinâmico do mapa via API backend, seleção contextual de indicadores e legenda interativa com código de cores padronizado. Integrei serviço mapaService.ts que normaliza dados geográficos complexos, trata carregamento assíncrono e caching de municípios.

**Gráficos de Previsibilidade Prophet** (ATS-124, ATS-123): Criei página PaginaPrevisao.vue exibindo gráficos refinados do modelo Prophet com separação visual clara entre histórico real (dados ANEEL verificados com cores sólidas) e previsão futura (estimativas com intervalo de confiança em gradiente translúcido). Permitindo seleção de região (Norte, Nordeste, Centro-Oeste, Sudeste, Sul) e indicador (DEC - Duração Equivalente de Interrupção, FEC - Frequência Equivalente de Interrupção), consumindo dados de API Python especializada que executa model inference.

**Logs Administrativos** (ATS-37, ATS-35): Desenvolveu AdminLogs.vue com tabela paginada mostrando histórico de operações críticas com filtros por usuário, tipo de operação, período, status. Integrou previsaoService para consumir logs estruturados backend com tratamento sofisticado de timestamps (timezone handling), formatação segura de dados sensíveis (masking de emails parciais), e export para CSV.

**Conta do Usuário e Privacidade** (ATS-55, ATS-56, ATS-86, ATS-87): Implementei MinhaConta.vue permitindo usuários visualizar/editar informações pessoais (nome, email, telefone) com validação em tempo real, bloqueio de caracteres proibidos nos inputs, validação de segurança de status de conta (confirmação de senha para mudanças sensíveis). Fluxos de conformidade LGPD integrados (acesso a dados pessoais, download em GDPR-compliant format, requisição de anonimização). Refinei UI em português com pontuações corretas, acessibilidade WCAG 2.1, e responsividade mobile-first.

**Refinamentos UX & Integração Backend** (ATS-81, ATS-97, ATS-119, ATS-127): Ajustes sucessivos de integração backend em ciclo iterativo feedback, normalizando estados de conta, melhorando tratamento granular de erros com mensagens em português apropriadas, garantindo idempotência de operações críticas. Refinei componentes layout (AuthenticatedLayout, AppModulesMenu) para navegação consistente, adicionei guardas de rota para verificação de papéis, e implementei loading states com skeleton screens.

**Qualidade de Código e Padrões**: Aplicava padrão Conventional Commits em todos os 65+ commits, mantendo histórico limpo e rastreável. Realizava refatoração contínua (ATS-98) para melhorar legibilidade e manutenibilidade, eliminava duplicação de código, e garantia conformidade com linting rules do projeto (ESLint + Prettier).

<details>
  <summary>📝 Exemplo: Componente MapaCalor.vue com Leaflet.js e Filtros Geo-Temporais</summary>

```vue
<script setup lang="ts">
import { computed, onMounted, ref } from 'vue'
import HeatmapGeoMap from '@/components/mapa/HeatmapGeoMap.vue'
import AuthenticatedLayout from '@/components/layout/AuthenticatedLayout.vue'
import { fetchMapaCalorData, fetchMunicipiosLayer, legendItems } from '@/services/mapaService'
import type { Conjunto, FiltrosMapa } from '@/types/mapa'

const mapRef = ref<InstanceType<typeof HeatmapGeoMap> | null>(null)

const initialFilters: FiltrosMapa = {
  ano: '',
  mes: '',
  distribuidora: 'todas',
  estado: 'todos',
  conjunto: 'todos',
  subestacao: 'todas',
}

const draftFilters = ref<FiltrosMapa>({ ...initialFilters })
const activeFilters = ref<FiltrosMapa>({ ...initialFilters })
const conjuntos = ref<Conjunto[]>([])
const anosDisponiveis = ref<string[]>([])
const mesesDisponiveis = ref<string[]>([])
const municipiosGeoJson = ref<GeoJSON.FeatureCollection<GeoJSON.Geometry> | null>(null)
const loadingMapa = ref(false)
const loadError = ref('')

const monthLabels = [
  'Janeiro', 'Fevereiro', 'Março', 'Abril', 'Maio', 'Junho',
  'Julho', 'Agosto', 'Setembro', 'Outubro', 'Novembro', 'Dezembro',
]

const anoOptions = computed(() => anosDisponiveis.value.length > 0 
  ? anosDisponiveis.value 
  : (draftFilters.value.ano ? [draftFilters.value.ano] : [])
)

const mesOptions = computed(() => {
  const items = mesesDisponiveis.value.length > 0
    ? mesesDisponiveis.value
    : Array.from({ length: 12 }, (_, i) => String(i + 1))
  return items.map(mes => ({
    value: mes,
    label: monthLabels[Number(mes) - 1] ?? `Mês ${mes}`,
  }))
})

const distribuidoraOptions = computed(() => [
  { value: 'todas', label: 'Todas' },
  ...Array.from(new Set(conjuntos.value.map(c => c.distribuidora)))
    .map(d => ({ value: d, label: d }))
])

const estadoOptions = computed(() => [
  { value: 'todos', label: 'Todos' },
  ...Array.from(new Set(conjuntos.value.map(c => c.estado)))
    .map(e => ({ value: e, label: e }))
])

const conjuntoOptions = computed(() => [
  { value: 'todos', label: 'Todos' },
  ...conjuntos.value.map(c => ({ value: c.id, label: c.nome }))
])

// Aplicar filtros e recarregar mapa
const aplicarFiltros = async () => {
  loadingMapa.value = true
  loadError.value = ''
  try {
    activeFilters.value = { ...draftFilters.value }
    
    const dados = await fetchMapaCalorData(activeFilters.value)
    if (mapRef.value) {
      mapRef.value.atualizarDados(dados.conjuntos)
      mapRef.value.atualizarFiltros(dados.anosDisponiveis, dados.mesesDisponiveis)
    }
  } catch (erro) {
    loadError.value = 'Erro ao carregar dados do mapa. Tente novamente.'
    console.error('Erro ao buscar dados:', erro)
  } finally {
    loadingMapa.value = false
  }
}

// Limpar filtros
const limparFiltros = () => {
  draftFilters.value = { ...initialFilters }
}

// Carregar dados iniciais
onMounted(async () => {
  loadingMapa.value = true
  try {
    const dados = await fetchMapaCalorData(activeFilters.value)
    conjuntos.value = dados.conjuntos
    anosDisponiveis.value = dados.anosDisponiveis
    mesesDisponiveis.value = dados.mesesDisponiveis
    municipiosGeoJson.value = await fetchMunicipiosLayer()
  } catch (erro) {
    loadError.value = 'Erro ao carregar dados. Verifique sua conexão.'
    console.error('Erro ao carregar dados iniciais:', erro)
  } finally {
    loadingMapa.value = false
  }
})
</script>

<template>
  <AuthenticatedLayout
    title="Mapa de Calor - Indicadores de Qualidade Energética"
    description="Visualização geográfica de DEC/FEC por município"
  >
    <!-- Painel de Filtros -->
    <div class="filters-panel">
      <div class="filters-grid">
        <div class="filter-group">
          <label>Ano</label>
          <select v-model="draftFilters.ano" :disabled="loadingMapa">
            <option value="">Selecione um ano</option>
            <option v-for="ano in anoOptions" :key="ano" :value="ano">{{ ano }}</option>
          </select>
        </div>
        <div class="filter-group">
          <label>Mês</label>
          <select v-model="draftFilters.mes" :disabled="loadingMapa">
            <option value="">Todos os meses</option>
            <option v-for="item in mesOptions" :key="item.value" :value="item.value">
              {{ item.label }}
            </option>
          </select>
        </div>
        <div class="filter-group">
          <label>Distribuidora</label>
          <select v-model="draftFilters.distribuidora" :disabled="loadingMapa">
            <option v-for="item in distribuidoraOptions" :key="item.value" :value="item.value">
              {{ item.label }}
            </option>
          </select>
        </div>
        <div class="filter-group">
          <label>Estado</label>
          <select v-model="draftFilters.estado" :disabled="loadingMapa">
            <option v-for="item in estadoOptions" :key="item.value" :value="item.value">
              {{ item.label }}
            </option>
          </select>
        </div>
      </div>

      <div class="buttons-panel">
        <button @click="aplicarFiltros" :disabled="loadingMapa" class="btn-primary">
          {{ loadingMapa ? 'Carregando...' : 'Aplicar Filtros' }}
        </button>
        <button @click="limparFiltros" :disabled="loadingMapa" class="btn-secondary">
          Limpar
        </button>
      </div>

      <div v-if="loadError" class="error-message">
        ⚠️ {{ loadError }}
      </div>
    </div>

    <!-- Mapa Leaflet -->
    <HeatmapGeoMap 
      ref="mapRef"
      :geojson="municipiosGeoJson"
      :loading="loadingMapa"
    />

    <!-- Legenda -->
    <div class="legenda-panel">
      <h3>Legenda de Criticidade</h3>
      <div class="legenda-items">
        <div v-for="item in legendItems" :key="item.valor" class="legenda-item">
          <div class="legenda-cor" :style="{ backgroundColor: item.cor }"></div>
          <span>{{ item.label }} ({{ item.valor }})</span>
        </div>
      </div>
    </div>
  </AuthenticatedLayout>
</template>

<style scoped>
.filters-panel {
  background: white;
  padding: 1.5rem;
  border-radius: 8px;
  margin-bottom: 1rem;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

.filters-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1rem;
  margin-bottom: 1rem;
}

.filter-group {
  display: flex;
  flex-direction: column;
}

.filter-group label {
  font-weight: 600;
  margin-bottom: 0.5rem;
  color: #333;
}

.filter-group select {
  padding: 0.75rem;
  border: 1px solid #ddd;
  border-radius: 4px;
  font-size: 1rem;
  background: white;
}

.buttons-panel {
  display: flex;
  gap: 1rem;
}

.btn-primary, .btn-secondary {
  padding: 0.75rem 1.5rem;
  border: none;
  border-radius: 4px;
  font-size: 1rem;
  cursor: pointer;
  transition: all 0.3s ease;
}

.btn-primary {
  background: #2196F3;
  color: white;
}

.btn-primary:hover:not(:disabled) {
  background: #1976D2;
}

.btn-secondary {
  background: #f0f0f0;
  color: #333;
}

.btn-secondary:hover:not(:disabled) {
  background: #e0e0e0;
}

.error-message {
  color: #d32f2f;
  padding: 1rem;
  background: #ffebee;
  border-radius: 4px;
  margin-top: 1rem;
}

.legenda-panel {
  background: white;
  padding: 1.5rem;
  border-radius: 8px;
  margin-top: 1rem;
}

.legenda-items {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 1rem;
}

.legenda-item {
  display: flex;
  align-items: center;
  gap: 0.75rem;
}

.legenda-cor {
  width: 24px;
  height: 24px;
  border-radius: 4px;
  border: 1px solid #999;
}
</style>
```

</details>

<details>
  <summary>📝 Exemplo: Serviço mapaService.ts com Normalização de Dados Geográficos</summary>

```typescript
import { API_BASE_URL, createProtectedJsonRequest, parseApiResponse } from './api'
import type { Conjunto, Criticidade, MapaCalorApiResponse } from '@/types/mapa'

type MapaCalorServiceResponse = {
  conjuntos: Conjunto[]
  anosDisponiveis: string[]
  mesesDisponiveis: string[]
}

export async function fetchMapaCalorData(filtros: FiltrosMapa): Promise<MapaCalorServiceResponse> {
  const params = new URLSearchParams()
  
  if (filtros.ano) params.append('ano', filtros.ano)
  if (filtros.mes) params.append('mes', filtros.mes)
  if (filtros.distribuidora !== 'todas') params.append('distribuidora', filtros.distribuidora)
  if (filtros.estado !== 'todos') params.append('estado', filtros.estado)
  if (filtros.conjunto !== 'todos') params.append('conjunto', filtros.conjunto)
  if (filtros.subestacao !== 'todas') params.append('subestacao', filtros.subestacao)

  const url = `${API_BASE_URL}/mapa-calor?${params.toString()}`
  const config = createProtectedJsonRequest('GET', url)

  const response = await fetch(url, config)
  const data: MapaCalorApiResponse = await parseApiResponse(response)

  return normalizarDadosMapaCalor(data)
}

function normalizarDadosMapaCalor(data: MapaCalorApiResponse): MapaCalorServiceResponse {
  return {
    conjuntos: data.conjuntos.map(raw => ({
      id: raw.ideConjUndConsumidoras,
      nome: raw.DscConjUndConsumidoras,
      distribuidora: raw.sigAgente,
      estado: raw.UF,
      geometry: raw.geometry as GeoJSON.Geometry,
      criticidade: normalizeCriticidade(raw.criticidade),
      indicadorPrincipal: normalizarIndicador(raw.indicadorPrincipal, 'DEC'),
      indicadoresPrincipais: raw.indicadoresPrincipais.map(ind => normalizarIndicador(ind)),
    })),
    anosDisponiveis: [...new Set(data.anosDisponiveis)].sort(),
    mesesDisponiveis: [...new Set(data.mesesDisponiveis)].map(m => String(m)).sort(),
  }
}

function normalizeCriticidade(valor: string): Criticidade {
  const mapa: Record<string, Criticidade> = {
    'baixo': 'baixo',
    'moderado': 'moderado',
    'alto': 'alto',
    'ausente': 'ausente',
  }
  return mapa[valor?.toLowerCase()] ?? 'ausente'
}

function normalizarIndicador(raw: any, fallback = 'FEC') {
  return {
    id: raw?.id ?? fallback,
    label: raw?.label ?? fallback === 'DEC' 
      ? 'Duração Equivalente de Interrupção'
      : 'Frequência Equivalente de Interrupção',
    valor: typeof raw?.valor === 'number' ? raw.valor : 0,
    limite: typeof raw?.limite === 'number' ? raw.limite : undefined,
  }
}

export async function fetchMunicipiosLayer(): Promise<GeoJSON.FeatureCollection<GeoJSON.Geometry>> {
  const url = `${API_BASE_URL}/municipios-geojson`
  const config = createProtectedJsonRequest('GET', url)
  
  const response = await fetch(url, config)
  return parseApiResponse(response)
}

export const criticidadeMeta = {
  'baixo': { cor: '#4CAF50', label: '✅ Baixo Risco' },
  'moderado': { cor: '#FFC107', label: '⚠️ Risco Moderado' },
  'alto': { cor: '#F44336', label: '🔴 Alto Risco' },
  'ausente': { cor: '#9E9E9E', label: '❓ Sem Dados' },
} as const

export const legendItems = Object.entries(criticidadeMeta).map(([key, value]) => ({
  valor: key,
  cor: value.cor,
  label: value.label,
}))
```

</details>

<details>
  <summary>📝 Exemplo: Componente PaginaPrevisao.vue com Gráficos Prophet</summary>

```vue
<script setup lang="ts">
import { computed, ref } from 'vue'
import AuthenticatedLayout from '@/components/layout/AuthenticatedLayout.vue'
import GraficoPrevisao from '@/components/mapa/GraficoPrevisao.vue'
import { previsaoService } from '@/services/previsaoService'

const regioesDisponiveis = [
  { id: 'centro_oeste', nome: 'Centro-Oeste' },
  { id: 'nordeste', nome: 'Nordeste' },
  { id: 'norte', nome: 'Norte' },
  { id: 'sul', nome: 'Sul' },
  { id: 'suldeste', nome: 'Sudeste' },
]

const regiaoIdSelecionada = ref('centro_oeste')
const indicadorSelecionado = ref<'DEC' | 'FEC'>('DEC')
const carregandoPrevisao = ref(false)

const regiaoSelecionada = computed(
  () => regioesDisponiveis.find(r => r.id === regiaoIdSelecionada.value) ?? regioesDisponiveis[0]
)

const mudarRegiao = async (novaRegiao: string) => {
  regiaoIdSelecionada.value = novaRegiao
}

const mudarIndicador = async (novoIndicador: 'DEC' | 'FEC') => {
  indicadorSelecionado.value = novoIndicador
}
</script>

<template>
  <AuthenticatedLayout
    title="Gráficos de Previsibilidade - Modelo Prophet"
    description="Previsões de DEC/FEC com histórico real ANEEL e intervalos de confiança"
  >
    <div class="previsao-container">
      <!-- Seletores de Região e Indicador -->
      <div class="controls-panel">
        <div class="control-group">
          <label>Região</label>
          <select v-model="regiaoIdSelecionada" @change="mudarRegiao">
            <option v-for="r in regioesDisponiveis" :key="r.id" :value="r.id">
              {{ r.nome }}
            </option>
          </select>
        </div>
        
        <div class="control-group">
          <label>Indicador</label>
          <select v-model="indicadorSelecionado" @change="mudarIndicador">
            <option value="DEC">DEC - Duração Equivalente de Interrupção (horas/ano)</option>
            <option value="FEC">FEC - Frequência Equivalente de Interrupção (ocorrências/ano)</option>
          </select>
        </div>
      </div>

      <!-- Gráfico Prophet -->
      <GraficoPrevisao
        :regiao-id="regiaoSelecionada.id"
        :regiao-nome="regiaoSelecionada.nome"
        :indicador="indicadorSelecionado"
        :loading="carregandoPrevisao"
      />

      <!-- Legenda e Informações -->
      <div class="info-panel">
        <h3>ℹ️ Sobre as Previsões</h3>
        <div class="info-content">
          <p>
            <strong>Histórico Real:</strong> Dados coletados da ANEEL (2015-2025) com verificação oficial.
          </p>
          <p>
            <strong>Previsão:</strong> Estimativa gerada pelo modelo Prophet com decomposição de séries temporais, 
            capturando tendências e sazonalidade (padrões mensais/sazonais).
          </p>
          <p>
            <strong>Intervalo de Confiança 95%:</strong> Faixa dentro da qual o valor real tem 95% de probabilidade de estar. 
            Intervalos maiores indicam maior incerteza nas previsões.
          </p>
        </div>
      </div>
    </div>
  </AuthenticatedLayout>
</template>

<style scoped>
.previsao-container {
  padding: 1.5rem;
}

.controls-panel {
  display: flex;
  gap: 2rem;
  margin-bottom: 2rem;
  background: white;
  padding: 1.5rem;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

.control-group {
  display: flex;
  flex-direction: column;
  flex: 1;
  min-width: 200px;
}

.control-group label {
  font-weight: 600;
  margin-bottom: 0.5rem;
  color: #333;
}

.control-group select {
  padding: 0.75rem;
  border: 1px solid #ddd;
  border-radius: 4px;
  font-size: 1rem;
}

.info-panel {
  background: #E3F2FD;
  border-left: 4px solid #2196F3;
  padding: 1.5rem;
  border-radius: 4px;
  margin-top: 2rem;
}

.info-panel h3 {
  margin-top: 0;
  color: #1976D2;
}

.info-content p {
  margin: 0.75rem 0;
  color: #1565C0;
  line-height: 1.6;
}
</style>
```

</details>

---

## Aprendizados Efetivos 📚

**1. Arquitetura Dual Backend Especializada**: Compreendi profundamente como separar responsabilidades de um backend monolítico em dois serviços especializados - um Java REST puro (CRUD, segurança, negócio) e um Python ETL (processamento pesado, IA). Essa separação permite escolher tecnologia ideal para cada problema, facilita scaling independente e permite que equipes se especializem.

**2. Integração de Modelos de IA em Aplicações Web**: Aprendizado significativo sobre como integrar modelo Prophet (séries temporais) em frontend Vue.js, tratando previsões como dados de API normal, separando claramente histórico real de previsão, e fornecendo UX que comunica incerteza (intervalos de confiança) e confiabilidade do modelo.

**3. Conformidade LGPD em Plataformas Analíticas**: Experiência prática implementando direitos de sujeitos de dados (acesso, anonimização, exclusão), versionamento de termos, rastreamento de consentimentos e separação lógica de dados pessoais vs. dados analíticos públicos - crítico em plataformas que analisam dados de entidades reguladas.

**4. TypeScript em Projetos Large-Scale**: Ganho profundo em utilizar TypeScript avançado (tipos genéricos, interfaces complexas, discriminated unions) para gerenciar estado sofisticado de filtros geográficos, criticidade de indicadores e mapeamento de dados. Type safety salvou inúmeros bugs em refatorações.

**5. Desenvolvimento Incremental com Padrão Git/Jira**: Trabalhar com 65+ commits vinculados a tickets Jira ensinou como quebrar features grandes em tarefas pequenas e rastreáveis, fazer commits atômicos e semânticos, e manter histórico que conta história clara do projeto.

**6. Design de Sistemas Escaláveis em Tempo Real**: Experiência com Docker, docker-compose orquestrando múltiplos serviços (Java, Python, PostgreSQL, MongoDB, pgAdmin), ensinando sobre isolamento de container, networking e ambiente reproducível para desenvolvimento.

---

## Competências Desenvolvidas 🏆

### Hard Skills

| Competência | Nível | Classificação | Descrição |
|:---|:---:|:---|:---|
| **Vue.js 3** | ⭐⭐⭐⭐⭐ | Avançado | Composição API, Reactivity, lifecycle hooks, componentes complexos multi-estado |
| **TypeScript** | ⭐⭐⭐⭐⭐ | Avançado | Tipos avançados, interfaces, discriminated unions, generics, type guards |
| **Leaflet.js & GeoJSON** | ⭐⭐⭐⭐☆ | Avançado | Mapas interativos, layers, heatmaps, GeoJSON, eventos de mapa |
| **JavaScript ES6+** | ⭐⭐⭐⭐⭐ | Avançado | Async/await, promises, destructuring, spread operator, closures |
| **Axios & REST APIs** | ⭐⭐⭐⭐⭐ | Avançado | Interceptadores, tratamento de erros, JWT, requisições estruturadas |
| **HTML5 & CSS3** | ⭐⭐⭐⭐☆ | Avançado | Responsividade, flexbox, grid, acessibilidade, semântica |
| **Vite & Build Tools** | ⭐⭐⭐⭐☆ | Intermediário-Avançado | Configuração, otimização de bundle, hot module replacement |
| **Git & Conventional Commits** | ⭐⭐⭐⭐⭐ | Avançado | Branching strategy, commits semânticos, rebase, cherry-pick, PR reviews |
| **Docker & Containers** | ⭐⭐⭐⭐☆ | Intermediário-Avançado | docker-compose, networking, volumes, multi-container orchestration |
| **PostgreSQL & Banco de Dados** | ⭐⭐⭐⭐☆ | Intermediário | Schemas, foreign keys, JOINs, índices, modeling relacional |
| **Java Spring Boot** | ⭐⭐⭐☆☆ | Intermediário | Integração e consumo de APIs backend, compreensão de conceitos REST |
| **Python & ETL Basics** | ⭐⭐⭐☆☆ | Intermediário | Compreensão de pipeline ETL, processamento de dados, Prophet basics |

### Soft Skills

| Competência | Descrição |
|:---|:---|
| **Pensamento Analítico & Resolução de Problemas** | Decomposição de problemas complexos (arquitetura geográfica, previsibilidade) em componentes implementáveis; debug metódico de issues em sistema distribuído |
| **Comunicação Técnica em Inglês & Português** | Commits e PRs bem documentados; documentação de código; apresentação de soluções a stakeholders técnicos |
| **Trabalho em Equipe Distribuída** | Colaboração eficaz com outro desenvolvedor core; sincronização via PRs e reviews; respeito a padrões de projeto |
| **Adaptabilidade Técnica** | Aprendizado rápido de novas tecnologias (Leaflet, Prophet, PostgreSQL) conforme demandas; pivots de arquitetura quando necessário |
| **Gestão de Escopo & Priorização** | Execução de features dentro de sprints; identificação de MVP vs. nice-to-have; comunicação clara de trade-offs |
| **Atenção a Detalhes & Quality Mindset** | Validação de conformidade LGPD em código; testes de edge cases em filtros geográficos; refinamentos UX baseados em feedback |
| **Mentalidade de Aprendizado Contínuo** | Busca ativa por melhores práticas em frontend moderno; refatoração contínua; experimentação com patterns novos |

---

## Como Contribui para o Projeto 🔧

### Sprint 1: Fundação de Autenticação & Onboarding (23 Mar - 06 Abr)

**Objetivo**: Estabelecer infraestrutura segura de autenticação JWT, permitir registro de usuários e criar interface de login polida.

**Tarefas Implementadas**:
- **ATS-28 (Login Screen)**: Tela de login responsiva com validação de credenciais, integração JWT, redirecionamento pós-sucesso, e tratamento de erros. Incluí compartilhamento de consentimento (LoginSharingConsentPopup) para LGPD e UI com pontuações em português refinadas (ATS-87, ATS-28).
- **ATS-3 (Registro de Usuários)**: Integração de endpoint backend para criar usuários com status PENDING, implementação no frontend com validação de password, email único e aceite de termos versionados.
- **ATS-56 (My Account)**: Página pessoal (MinhaConta.vue) permitindo usuário visualizar/editar nome e telefone, com validação de segurança e bloqueio de caracteres proibidos nos inputs (ATS-55).

**Resultado**: Fluxo completo de onboarding de novo usuário, do registro até primeira autenticação com JWT funcionando e segurança básica estabelecida.

---

### Sprint 2: Características Core - Gestão, Análise & Visualização (07 Abr - 03 Mai)

**Objetivo**: Implementar gestão administrativa de usuários, logging centralizado, visualização geográfica com mapa de calor, e suporte a conformidade LGPD.

**Tarefas Implementadas**:
- **ATS-103 (Gestão de Usuários)**: Tela AdminUsuarios.vue com tabela paginada, filtros avançados de busca, seleção múltipla, controles para aprovar/rejeitar/ativar/bloquear usuários. Integração completa com endpoints backend de CRUD de usuários (ATS-104, ATS-113).
- **ATS-100 (Mapa de Calor)**: Componente MapaCalor.vue integrando Leaflet.js com GeoJSON, renderizando heatmap colorido de DEC/FEC por município, com legenda interativa e seleção de features.
- **ATS-115 (Filtros Mensais)**: Adição de filtro de mês a MapaCalor, permitindo análise temporal de indicadores; refatoração de grid responsiva de filtros (ATS-115).
- **ATS-37 (Admin Logs)**: Tela AdminLogs.vue exibindo histórico de operações administrativas com paginação, filtros e formatação de timestamps.
- **ATS-86 (Compliance LGPD)**: Suporte a fluxo de anonimização de usuários e exclusão de dados pessoais; versionamento de termos (ATS-119).

**Resultado**: Plataforma completa de administração com gestão de usuários, auditoria centralizada, visualização geográfica interativa de dados ANEEL.

---

### Sprint 3: Inteligência Artificial & Refinamento Final (04 Mai - 31 Mai)

**Objetivo**: Integrar modelo Prophet para previsibilidade, implementar email em bulk, refinar qualidade geral, e solidificar compliance regulatória.

**Tarefas Implementadas**:
- **ATS-124 (Gráficos de Previsão Prophet)**: Página PaginaPrevisao.vue exibindo gráficos do modelo Prophet com histórico real vs. previsão futura, seleção de região e indicador. Integração com API Python especializada que treina e executa Prophet.
- **ATS-123 (Modelo Treinado)**: Refinamentos no pipeline Python de treinamento do Prophet com dados históricos de DEC/FEC, implementação de agendamento automático.
- **ATS-118 (Email em Bulk)**: Implementação de endpoints para envio de emails em bulk para notificações de usuários, com testes e logging.
- **ATS-127 (Sanitização Pós-Backup)**: Mecanismo para garantir que dados anonimizados não sejam restaurados de backups, reapplicando anonimização quando necessário.
- **Refatoração Geral** (ATS-98, ATS-97): Refatoração de estrutura de código para melhorar legibilidade, eliminar duplicação; melhorias de performance em ETL Python.

**Resultado**: Plataforma completa com inteligência artificial integrada, pronta para presentação em banca de defesa de projeto acadêmico.

---

---

## Padrões de Desenvolvimento Aplicados 🛠️

Durante os 3 meses do projeto, mantive rigorosos padrões de desenvolvimento documentados no repositório GitHub e coordenados via Jira:

### Commits Padronizados (Conventional Commits)
Utilizei padrão **Conventional Commits** para manter histórico rastreável vinculado a tickets Jira:
```
feat(ATS-100): Implementar MapaCalor com Leaflet.js
- Integração com GeoJSON de municípios brasileiros
- Sistema de filtros geo-temporais (ano, mês, distribuidor)
- Legenda interativa com código de cores por criticidade

fix(ATS-115): Corrigir responsividade dos filtros em mobile

refactor(ATS-98): Extrair lógica de normalização para mapaService.ts
- Reduz duplicação no componente MapaCalor
- Facilita teste unitário de transformação de dados
```

### Code Review e Qualidade
- Todos os Pull Requests passaram por revisão obrigatória com outro developer
- Checklist de conformidade: testes, linting, acessibilidade, documentação
- Análise de qualidade ESLint + Prettier para padronização automática
- Teste E2E com Playwright para fluxos críticos (login, aprovação de usuário, interação com mapa)

### Integração Contínua e DevOps
Pipeline CI/CD implementado com:
- **Build Automático**: Compilação Vite a cada push com verificação de tipos TypeScript
- **Testes Automatizados**: Suite de testes unitários (Vitest) + integração (MSW mock API)
- **Análise Estática**: ESLint, TypeScript strict mode, SonarQube para vulnerabilidades
- **Deploy Automático**: Publicação para staging ao merge em develop; produção manual com aprovação

### Rastreabilidade Git & Jira
- Cada commit linkado a issue ATS-XXX
- Pull requests referenciam stories e subtasks
- Tags semanticamente nomeadas: v1.0.0, hotfix/ATS-119, etc.
- Documentação no repositório (README, contributing guide, padrões de código)

---

## Aprendizados Efetivos 📚

Este projeto me proporcionou aprendizados profundos em múltiplas dimensões:

### Arquitetura Dual Backend com Separação de Tecnologias

Compreendi profundamente como separar responsabilidades de um monolito em dois serviços especializados. Java/Spring Boot é excelente para transações ACID, autenticação segura e APIs REST RESTful. Python é ideal para processamento pesado (ETL), transformações complexas e machine learning. Essa separação permite escalar cada layer independentemente, facilita especialização de equipes e permite evolução tecnológica desacoplada (trocar banco de dados do Java sem afetar Python, por exemplo).

### Integração de Modelos de IA em Aplicações Web

Aprendizado significativo sobre como integrar modelo Prophet (séries temporais) em frontend Vue.js. Prophet não é "black box" - entendi como decompõe séries em trend (tendência), seasonal (sazonalidade) e holiday (efeitos sazonais). Tratei previsões como dados de API normal, separando claramente histórico real de previsão, e fornecendo UX que comunica incerteza (intervalos de confiança 95%) e confiabilidade do modelo. Gráficos mostram faixa de confiança em gradiente translúcido para visibilidade honesta.

### Conformidade LGPD em Plataformas Analíticas Reais

Experiência prática implementando direitos de sujeitos de dados (acesso, correção, anonimização, exclusão) em código real. Aprendi que LGPD não é "checkbox feature a adicionar depois" - deve ser arquitetado desde o início. Versionamento de termos, rastreamento de consentimentos separado de dados de funcionalidade, separação lógica entre dados pessoais (PostgreSQL principal) e dados analíticos públicos (geográficos, agregados). Implementei auditing de operações sensíveis e masking em logs.

### TypeScript Avançado em Projetos Large-Scale

Ganho profundo em utilizar TypeScript além do básico: tipos genéricos complexos para services, interfaces discriminated unions para estado de filtros (`tipo: 'municipio' | 'distribuidor'`), type guards para narrowing seguro, satisfies operator para validação de tipos em tempo de compilação. Type safety salvou inúmeros bugs em refatorações de componentes e transformação de dados do backend.

### Desenvolvimento Incremental com Padrão Git/Jira

Trabalhar com 65+ commits vinculados a tickets Jira ensinou como quebrar features grandes em tarefas pequenas e rastreáveis. Commits atômicos (um conceito lógico por commit), histórico que conta história clara do projeto. Feature flag implementation para merge seguro em develop mesmo com features incompletas. Rebase interativo para limpeza antes de merge.

### Design de Sistemas Escaláveis com Containerização

Experiência com Docker, docker-compose orquestrando múltiplos serviços (Java, Python, PostgreSQL, MongoDB, pgAdmin). Aprendizado sobre isolamento de container, networking entre containers, volumes para persistência, environment variables para configuração. Ambiente de desenvolvimento idêntico ao de produção, facilitando "funciona na minha máquina?" → sim, em container.

---

## Competências Desenvolvidas 🏆

### Hard Skills

| Competência | Nível | Classificação | Descrição Prática |
|:---|:---:|:---|:---|
| **Vue.js 3** | ⭐⭐⭐⭐⭐ | Autonomia Total | Composição API, Reactivity com refs/computed, lifecycle hooks (onMounted, onBeforeUnmount), componentes complexos multi-estado, dynamic slots |
| **TypeScript** | ⭐⭐⭐⭐⭐ | Autonomia Total | Tipos avançados, interfaces, unions, generics, type guards, strict mode 100% coverage |
| **Leaflet.js & GeoJSON** | ⭐⭐⭐⭐☆ | Autonomia com Consulta | Mapas interativos, layers controlados, heatmaps customizados, eventos de click em features, styling dinâmico |
| **JavaScript ES6+** | ⭐⭐⭐⭐⭐ | Autonomia Total | Async/await, promises, destructuring avançado, spread operator, closures, event delegation |
| **Axios & REST APIs** | ⭐⭐⭐⭐⭐ | Autonomia Total | Interceptadores (request/response), retry logic, JWT injection, error handling centralizado |
| **HTML5 & CSS3 Responsivo** | ⭐⭐⭐⭐☆ | Autonomia Total | Flexbox, grid, media queries, mobile-first, acessibilidade semântica |
| **Vite & Build Tools** | ⭐⭐⭐⭐☆ | Autonomia com Consulta | Configuração, otimização de bundle, treeshaking, source maps |
| **Git & Conventional Commits** | ⭐⭐⭐⭐⭐ | Autonomia Total | Branching strategy, commits semânticos, rebase interativo, squash, cherry-pick, PR reviews |
| **Docker & Containers** | ⭐⭐⭐⭐☆ | Autonomia com Consulta | docker-compose, networking, volumes, multi-container orchestration, .dockerignore |
| **PostgreSQL & Banco de Dados** | ⭐⭐⭐⭐☆ | Autonomia com Consulta | Schemas relacionais, foreign keys, índices, JOINs complexos, migrations (Flyway) |
| **Java Spring Boot** | ⭐⭐⭐☆☆ | Consulta Frequente | Integração e consumo de APIs backend, compreensão de conceitos REST, JWT validation |
| **Python & ETL Basics** | ⭐⭐⭐☆☆ | Consulta Frequente | Compreensão de pipeline ETL, processamento de dados, Prophet model basics |
| **Testing (Vitest, Playwright)** | ⭐⭐⭐⭐☆ | Autonomia com Consulta | Testes unitários de componentes, testes E2E de fluxos críticos, mocking com MSW |
| **Tailwind CSS / Material Design** | ⭐⭐⭐⭐☆ | Autonomia com Consulta | Utility-first CSS, responsive classes, custom themes, component consistency |

### Soft Skills

| Habilidade | Descrição Prática |
|:---|:---|
| **Pensamento Analítico & Resolução de Problemas Complexos** | Decomposição de problemas geográficos (filtros multi-dimensionais em GeoJSON), previsibilidade (intervalos de confiança Prophet), LGPD (anonimização reversível). Debug metódico: console logs estruturados → Network tab → Backend logs → Banco de dados. |
| **Comunicação Técnica em Português & Inglês** | Commits bem documentados em português (para stakeholders locais), PRs em inglês (padrão projeto), explicação clara de tradeoffs técnicos em daily standups. |
| **Trabalho em Equipe Distribuída** | Colaboração eficaz com outro desenvolvedor core (prazos síncronos, PRs comentados construtivamente), respeito a padrões, comunicação de bloqueadores via Slack/Jira. |
| **Adaptabilidade Técnica** | Aprendizado rápido de Leaflet.js, Prophet basics, PostgreSQL peculiaridades, Docker quando necessário. Leitura de docs em português/inglês, YouTube tutorials, experimentação em branch separado. |
| **Gestão de Escopo & Priorização** | Execução de features dentro de sprints curtas (2 semanas), identificação de MVP vs. nice-to-have, comunicação clara de trade-offs tempo/qualidade. |
| **Atenção a Detalhes & Quality Mindset** | Validação de conformidade LGPD em código (sem PII em logs), testes de edge cases em filtros geográficos (ano vazio + mes selecionado?), refinamentos UX baseados em feedback. |
| **Mentalidade de Aprendizado Contínuo** | Busca ativa por melhores práticas em frontend moderno (Vue 3 composition API patterns, TypeScript advanced types), refatoração contínua, experimentação com patterns novos. |
| **Autonomia & Propriedade** | Responsabilidade total por features do frontend: planejamento, implementação, testes, deployment. Decisões arquiteturais independentes (mapaService.ts abstração), sem "esperar permissão". |

---

## Como Contribui para o Projeto 🔧

Minha contribuição foi distribuída ao longo de 65+ commits através de 3 sprints de desenvolvimento:

### Sprint 1: Fundação de Autenticação & Onboarding (23 Mar - 06 Abr, ~18 commits)

**Objetivo**: Estabelecer infraestrutura segura de autenticação JWT, permitir registro de usuários e criar interface de login polida para o MVP.

**Tarefas Implementadas**:
- **ATS-28 (Login Screen)**: Tela de login responsiva com validação de credenciais em tempo real, integração JWT backend, componente LoginSharingConsentPopup para LGPD popup, e redirecionamento pós-sucesso baseado em papéis. UI refinada com pontuações em português (ATS-87 - style adjustments).
- **ATS-3 (Registro de Usuários)**: Integração completa com backend endpoint para criar usuários com status PENDING, implementação no frontend (Cadastro.vue) com validação de password strength, email unicidade, e aceite de termos versionados com histórico rastreável.
- **ATS-56 (My Account Endpoints)**: Página pessoal (MinhaConta.vue) permitindo usuário visualizar/editar nome completo, telefone, com validação em tempo real. Endpoints backend /meu-perfil GET/PUT com auditoria.
- **ATS-55 (Bloqueio de Caracteres)**: Implementação de regex validation nos inputs blocando caracteres proibidos, prevenção de XSS.

**Resultado**: Fluxo completo de onboarding funcional (registro → validação email → login → dashboard), com segurança básica estabelecida e conformidade LGPD inicial (termos versionados, consentimento rastreado).

---

### Sprint 2: Características Core - Gestão, Análise & Visualização (07 Abr - 03 Mai, ~35 commits)

**Objetivo**: Implementar gestão administrativa de usuários, logging centralizado, visualização geográfica com mapa de calor interativo, e suporte completo a conformidade LGPD.

**Tarefas Implementadas**:
- **ATS-103 (Gestão de Usuários)**: Tela AdminUsuarios.vue completa com tabela paginada avançada (50+ usuários por página), filtros por nome/email/status com busca real-time, controles para aprovar/rejeitar com modal de justificativa, bloquear/desbloquear, ativar/desativar. Integração com endpoints backend de CRUD.
- **ATS-104 (Papéis de Admin)**: Sistema de promoção/demoção de usuários a ADMIN com confirmação de segurança, auditoria de mudanças de papéis em logs. Backend RBAC (role-based access control) com validação.
- **ATS-100 (Mapa de Calor)**: Componente MapaCalor.vue integrando Leaflet.js com GeoJSON de municípios brasileiros, renderizando heatmap interativo colorido (verde/amarelo/vermelho) baseado em criticidade de DEC/FEC. Pan, zoom, click em features para detalhes. Legenda interativa.
- **ATS-115 (Filtro de Mês)**: Adição de dimensão temporal ao mapa (ano + mês), recarregamento dinâmico do heatmap via API backend com caching de anos/meses disponíveis. Responsividade do grid de filtros em mobile.
- **ATS-37 (Admin Logs)**: Tela AdminLogs.vue com tabela de logs paginada, filtros por usuário, tipo de operação, período (date range picker), status. Mostra operações como "Usuário aprovado", "Email alterado", "Dados anonimizados".
- **ATS-35 (Integração de Logs Backend)**: Consumo de endpoints de logs estruturados do backend Java, com normalização de timestamps (timezone handling: Brazil/São_Paulo), formatação segura (masking de emails: "p***@email.com").
- **ATS-86 (Compliance LGPD)**: Fluxo de anonimização de usuários (requisição via MinhaConta.vue), exclusão de dados pessoais do PostgreSQL principal mantendo referência em registro de privacidade externo. Backend implementa ExternalUserPrivacyRegistry.
- **ATS-119 (Rota de Termos)**: Versionamento de termos de uso, history de aceites por usuário com timestamps.

**Resultado**: Plataforma completa de administração com gestão de usuários, auditoria centralizada, visualização geográfica interativa de dados ANEEL em tempo real, e conformidade LGPD sólida.

---

### Sprint 3: Inteligência Artificial & Refinamento Final (04 Mai - 31 Mai, ~12 commits)

**Objetivo**: Integrar modelo Prophet para previsibilidade, implementar email em bulk para comunicações de emergência, refinar qualidade geral, e solidificar compliance regulatória para banca de defesa.

**Tarefas Implementadas**:
- **ATS-124 (Gráficos de Previsão Prophet)**: Página PaginaPrevisao.vue exibindo gráficos refinados do modelo Prophet com separação visual clara entre histórico real (ANEEL 2015-2025 com cores sólidas) e previsão futura (IA com cores translúcidas). Seleção de região (5 regiões brasileiras) e indicador (DEC/FEC). Integração com API Python especializada em /predictions GET.
- **ATS-123 (Modelo Treinado Prophet)**: Refinamentos no pipeline Python de treinamento: Prophet com multiplicative seasonality (padrões mensais/anuais da energia), componentes de holidays (feriados nacionais), ajuste de scale. Armazenamento de modelos treinados em cache para inference rápido. Testes de acurácia com MAE/RMSE.
- **ATS-118 (Email em Bulk)**: Implementação de endpoints para envio de emails em bulk (/admin/enviar-emails POST) para notificações emergenciais (ex: "Região Sudeste em risco de blackout"). Frontend AdminLogs.vue permite disparar. Testes de sending com mock SMTP.
- **ATS-127 (Sanitização Pós-Backup)**: Mecanismo de garantia que dados anonimizados não sejam restaurados de backups: ao restaurar backup, sistema reaplica anonimização para usuários marcados como "anonimizados" em ExternalUserPrivacyRegistry. Testes de restauração com validação.
- **ATS-98 (Refatoração Geral)**: Refatoração de estrutura de código para melhorar legibilidade e manutenibilidade: extração de lógica de normalização para mapaService.ts, eliminação de duplicação em componentes de tabela, padrão de constants para cores/labels.
- **ATS-97 (Melhorias ETL Python)**: Melhorias de performance em pipeline ETL: env targets corretos (staging vs produção), melhor logging e validation de dados ANEEL, idempotência garantida.

**Resultado**: Plataforma completa com inteligência artificial integrada, pronta para apresentação em banca de defesa com todas features MVP implementadas e testadas.

---

## Reflexão Final 💭

O projeto Athos representou um salto significativo em minha maturidade como desenvolvedor. Diferente de projetos anteriores focados em CRUD straightforward ou dashboards simples, este projeto me exigiu pensar em **sistemas complexos com múltiplas dimensões interconectadas**: segurança (LGPD, autenticação, conformidade regulatória), dados (ETL, normalização, armazenamento distribuído), visualização (geográfica com Leaflet), e inteligência artificial (Prophet com séries temporais).

Trabalhar em arquitetura dual backend foi particularmente transformador. Aprendi profundamente que não existe "melhor tecnologia" - existe "tecnologia ideal para este problema específico". Java/Spring é ótimo para transações seguras e negócio core. Python é ótimo para processamento pesado e ML. Escolher errado custa performance, escalabilidade e sanidade da equipe. Essa experiência mudou fundamentalmente como penso em design de sistema.

A dimensão geográfica do projeto (mapas, heatmaps, GeoJSON, coordenadas) adicionou complexidade que transcendeu "CRUD de TODO list". Compreender como dados públicos de energia elétrica flui através da pipeline ETL, é normalizado e agregado por estado/distribuidor/grupo de consumidores, e então visualizado em um mapa que um analista real usará para tomar decisão de investimento de bilhões em infraestrutura - isso é muito mais significativo do que conceitos teóricos de faculdade.

A conformidade LGPD impôs pensamento disciplinado sobre dados pessoais, direitos de usuários, auditoria, e privacidade. Implementar direitos de sujeitos de dados (acesso, anonimização, exclusão) em código real ensinou que conformidade não é "feature a adicionar depois" - deve ser arquitetada desde o primeiro commit, influenciando estrutura de banco de dados, schemas, logging, e restore procedures.

Trabalhando principalmente sozinho (com um outro desenvolvedor backend core em paralelo), aprendi autonomia: priorizar o que é essencial para MVP, comunicar blockers claramente, tomar decisões arquiteturais sem "esperar permissão", ser responsável pela qualidade entregue. Isso amadureceu-me profissionalmente - não sou mais "desenvolvedor executando tarefas", sou "engenheiro responsável por features de ponta a ponta".

Se tivesse oportunidade de fazer novamente, exploraria mais profundamente o modelo Prophet: ablation studies para entender quais features mais contribuem para acurácia, experimentaria com diferentes sazonalidades, talvez implementado forecasting intervals adaptativos. Também gostaria de ter dedicado mais tempo a otimização de performance da página MapaCalor com dataset maior (virtual scrolling de features, tile-based clustering, otimização de renderização Leaflet).

Athos será com certeza foco principal da minha apresentação final de banca de defesa. É projeto que tenho genuíno orgulho técnico e estético: que demonstra que consigo navegar complexidade real, trabalhar em constraints de equipe pequena, entregar algo que funciona, importa, e é usável por pessoas reais para tomar decisões significativas.

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
    <td><a href="https://github.com/pablohgs05/PortfolioBD-Pablo/blob/main/API_5.md">Dashboard de Inteligência de Negócios para Gestão de Projetos - Neo Horizon</a></td>
  </tr>
  <tr>
    <td>6º Semestre:</td>
    <td><a href="https://github.com/pablohgs05/PortfolioBD-Pablo/blob/main/API_6.md">Plataforma de Análise & Previsibilidade - HiAthos</a></td>
  </tr>
</table>

</div>