# API 6º Semestre - Plataforma de Análise e Previsibilidade de Indicadores de Qualidade de Energia Elétrica - ATHOS

<div align="center">
  <a href="https://github.com/AthosFatecSjc/Athos">
    <img src="https://img.shields.io/badge/GitHub-Repositório Projeto-181717?style=for-the-badge&logo=github" alt="Repositório">
  </a>
</div>

## Tema do Projeto 📋

**Plataforma de Análise e Previsibilidade de Indicadores de Qualidade de Energia Elétrica (HiATHOS)**

O projeto consiste em uma plataforma web desenvolvida em parceria com a TECSYS para análise de dados públicos da ANEEL. A solução centraliza, trata e organiza informações de distribuidoras de energia, transformando-as em indicadores estruturados de qualidade do serviço.
A aplicação permite visualização interativa por meio de mapas de calor, além de utilizar modelos de previsão para análise de indicadores como DEC e FEC. Também contempla gestão de usuários com controle de acesso, rastreabilidade de operações e uma arquitetura baseada em dois backends: um responsável pela API e outro pelo processamento e análise dos dados.


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

* **Vue.js 3**: Utilizado no desenvolvimento do frontend para construção de interfaces reativas e dinâmicas, incluindo dashboards, visualizações geográficas e páginas administrativas.

* **TypeScript**: Aplicado em todo o frontend para garantir tipagem estática, maior confiabilidade e organização em estruturas complexas de dados e integração com a API.

* **Java 21 / Spring Boot**: Responsável pelo backend principal da aplicação, oferecendo uma API REST com autenticação via JWT, controle de acesso por perfis e gerenciamento de dados.

* **Python**: Utilizado no processamento de dados e pipeline ETL, realizando coleta, tratamento e transformação de dados públicos da ANEEL.

* **Prophet**: Biblioteca de previsão de séries temporais empregada para análise de indicadores como DEC e FEC, permitindo geração de previsões com base em padrões históricos.

* **PostgreSQL**: Banco de dados relacional principal, responsável pelo armazenamento estruturado dos dados da aplicação e indicadores energéticos.

* **MongoDB**: Utilizado para armazenamento de logs e dados semi-estruturados, complementando o PostgreSQL em cenários que exigem maior flexibilidade.

* **Leaflet.js**: Biblioteca empregada na construção de mapas interativos para visualização geográfica dos indicadores.

* **Axios**: Cliente HTTP utilizado no frontend para comunicação com a API, incluindo gerenciamento de autenticação e tratamento de respostas.

* **Docker**: Utilizado para containerização e padronização do ambiente de desenvolvimento e execução da aplicação.

* **Git / Conventional Commits**: Controle de versão com padronização de commits, facilitando rastreabilidade e organização do desenvolvimento.

---

## Arquitetura e Estrutura do Projeto 🏗️

### Arquitetura Dual Backend

Este projeto adota uma arquitetura inovadora com **dois backends especializados** que se comunicam através de APIs RESTful e banco de dados compartilhado:

#### Backend Java (Spring Boot)
Responsável pela camada de aplicação e regras de negócio:
- Autenticação e autorização com JWT e controle por papéis (RBAC)
- Gestão de usuários (CRUD, aprovação, edição e auditoria)
- Conformidade LGPD (anonimização, controle de consentimento)
- Logging e auditoria de operações
- Persistência com JPA e versionamento via Flyway

#### Backend Python (ETL Pipeline)
Responsável pelo processamento e inteligência dos dados:
- Coleta automatizada de dados públicos da ANEEL
- Pipeline ETL com validação e normalização 
- Agregações geográficas e temporais 
- Modelos de previsão (Prophet) para indicadores DEC e FEC 
- Execução de jobs agendados 

### Cronograma de Desenvolvimento

**Timeline: 23 de Março - 31 de Maio de 2026 (3 meses, ~65 commits)**

- **Sprint 1 (23 Mar - 06 Abr)**: Fundação - Autenticação, Registro de Usuários, Login Screen, My Account endpoints (ATS-3, ATS-28, ATS-56)
- **Sprint 2 (07 Abr - 03 Mai)**: Core Features - Gestão de Usuários (ATS-104, ATS-103, ATS-113), Logs Administrativos (ATS-37, ATS-35), Compliance LGPD (ATS-86), Mapa de Calor com Leaflet (ATS-100), Filtros de Mês (ATS-115)
- **Sprint 3 (04 Mai - 31 Mai)**: IA & Refinamento - Gráficos de Previsão Prophet (ATS-124), Sanitização Pós-Backup (ATS-127), Email em Bulk (ATS-118), Modelo Treinado (ATS-123), Refinamentos finais

---

## Contribuições Individuais 🎯

### Desenvolvimento Full-Stack (Frontend Vue.js 3 + TypeScript)

Atuei principalmente no desenvolvimento full-stack com foco em frontend, sendo responsável pela implementação da interface da aplicação em Vue.js 3 com TypeScript e sua integração com os serviços backend.

Minhas contribuições abrangeram a construção das principais funcionalidades do sistema, incluindo autenticação e gestão de usuários, visualização de dados geográficos por meio de mapas interativos, exibição de previsões com modelos de séries temporais e painéis administrativos com logs e controles de acesso. Também participei ativamente da integração com APIs, tratamento de erros, organização da arquitetura frontend e padronização do código.

De forma geral, minha atuação envolveu o desenvolvimento completo da camada de apresentação e a garantia de uma experiência funcional, segura e consistente para o usuário.

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

### Rastreabilidade Git & Jira
- Cada commit linkado a issue ATS-XXX
- Pull requests referenciam stories e subtasks
- Tags semanticamente nomeadas: v1.0.0, hotfix/ATS-119, etc.
- Documentação no repositório (README, contributing guide, padrões de código)

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

## Contribuição individual por sprint 🔧

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

O projeto Athos representou um avanço significativo na minha formação ao integrar, em uma única solução, conceitos de arquitetura, tratamento de dados, visualização e inteligência artificial. A experiência reforçou a importância de escolher tecnologias adequadas para cada contexto, além de aplicar, na prática, aspectos como LGPD, escalabilidade e organização de sistemas. Também contribuiu diretamente para o desenvolvimento da minha autonomia e capacidade de tomada de decisão, consolidando minha evolução para atuar em projetos mais complexos e próximos de cenários reais.

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
