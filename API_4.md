# API 4º Semestre - Sistema de Processamento e Análise de Imagens Agrícolas - Visiona

<div align="center">
  <a href="https://github.com/PorygonAPI/Porygon3">
    <img src="https://img.shields.io/badge/GitHub-Repositório Projeto-181717?style=for-the-badge&logo=github" alt="Repositório">
  </a>
</div>

## Tema do Projeto 📋

**Sistema de Processamento e Análise de Imagens Agrícolas para a Visiona**

O projeto consiste em uma aplicação web desenvolvida para processar, visualizar e analisar imagens agrícolas com foco em detecção automática de ervas daninhas através de inteligência artificial. O sistema permite que consultores façam upload de áreas agrícolas via GeoJSON, analistas visualizem mapas de classificação automática gerados por IA, façam edições manuais das marcações quando necessário, e realizem aprovações com rastreamento de tempo. O sistema também fornece dashboards para consulta de métricas de produtividade e acompanhamento de atividades. **Neste semestre, a equipe adotou a prática de separação entre repositórios de client (frontend) e server (backend)**, permitindo desenvolvimento paralelo e maior escalabilidade.

## Cliente

**Visiona** - Empresa especializada em soluções geoespaciais e processamento de imagens agrícolas

## Tecnologias Adotadas 💻

<div align="center">
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original-wordmark.svg" width="100" height="100" alt="Java"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/spring/spring-original-wordmark.svg" width="100" height="100" alt="Spring Boot"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/vuejs/vuejs-original-wordmark.svg" width="100" height="100" alt="Vue.js"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original-wordmark.svg" width="100" height="100" alt="MySQL"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/docker/docker-original-wordmark.svg" width="100" height="100" alt="Docker"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/git/git-original-wordmark.svg" width="100" height="100" alt="Git"/>
</div>

### Descrição das Tecnologias

- **[Java 22](https://www.java.com/pt-BR/)**: Linguagem de programação orientada a objetos, robusta e escalável, utilizada para desenvolver o backend da aplicação com suporte a processamento assíncrono e manipulação eficiente de dados geoespaciais e imagens.

- **[Spring Boot 3.3.3](https://spring.io/projects/spring-boot)**: Framework para desenvolvimento ágil de aplicações Java, fornecendo componentes como Spring Data JPA para persistência de dados, Spring Web para exposição de APIs REST, e Spring Security para autenticação e autorização de usuários.

- **[Vue.js](https://vuejs.org/)**: Framework JavaScript progressivo utilizado para desenvolvimento do frontend, permitindo construção de interfaces dinâmicas e responsivas para visualização de mapas, edição de imagens e acesso a dashboards.

- **[MySQL](https://www.mysql.com/)**: Sistema de gerenciamento de banco de dados relacional de código aberto, utilizado para armazenar de forma estruturada dados geoespaciais, informações de usuários, áreas cadastradas, mapas de classificação e métricas de produtividade.

- **[Docker](https://www.docker.com/)**: Plataforma de containerização que permite empacotar a aplicação e suas dependências em containers isolados, facilitando deployment, escalabilidade e consistência entre ambientes de desenvolvimento, teste e produção.

- **[Git](https://git-scm.com/)**: Sistema de controle de versão distribuído utilizado para gerenciar o código-fonte do projeto, permitindo colaboração eficiente entre os membros da equipe através de commits, branches e pull requests.

- **[Leaflet](https://leafletjs.com/)**: Biblioteca JavaScript de código aberto para mapas interativos, integrada ao Vue.js para visualização de dados geoespaciais com camadas, marcadores e ferramentas de edição.

- **[GeoJSON](https://geojson.org/)**: Formato aberto baseado em JSON para codificação de estruturas de dados geográficas, utilizado para upload e manipulação de geometrias das áreas agrícolas no sistema.

---

## Arquitetura e Estrutura do Projeto 🏗️

### Separação entre Client e Server

**Neste semestre, o projeto marca uma transição importante na arquitetura do desenvolvimento.** A equipe adotou o padrão de separação entre repositórios independentes para frontend (client) e backend (server), permitindo:
- Desenvolvimento paralelo de equipes especializadas
- Independência de deployment e escalabilidade
- Facilidade de manutenção e evolução independente de cada camada
- Comunicação clara através de APIs bem documentadas

### Requisitos Funcionais

| Código | Requisito |
|--------|-----------|
| R1 | Cadastro de usuários com três papéis: administrador, analista e consultor |
| R2 | Visualização e edição de mapas de classificação automática |
| R3 | Cadastro de áreas agrícolas com informações consolidadas |
| R4 | Controle de permissões e acesso baseado em papéis |
| R5 | Upload de arquivos GeoJSON com validação |
| R6 | Armazenamento de informações: fazenda, cultura, produtividade, área, solo, cidade, estado |
| R7 | Dashboards com métricas de produtividade e acompanhamento |

### Requisitos Não-Funcionais

| Código | Requisito |
|--------|-----------|
| RN1 | Ferramenta interativa de desenho e edição de geometria |
| RN2 | Autenticação e autorização com Spring Security |
| RN3 | Logs de atividades (login, alterações, aprovações) |
| RN4 | Dados sensíveis protegidos conforme padrões de segurança |
| RN5 | Interface responsiva e amigável ao usuário |

### Cronograma de Desenvolvimento

- **Sprint 1** (24/02 - 28/02): Cadastro de usuários e áreas agrícolas, upload de GeoJSON
- **Sprint 2** (07/04 - 27/04): Visualização e edição de mapas de IA, análise de imagens
- **Sprint 3** (05/05 - 25/05): Dashboards, relatórios, segurança e autenticação

---

## Contribuições Individuais 🎯

### Desenvolvimento da API REST (Backend)

Como desenvolvedor backend, fui responsável pela implementação de endpoints REST robustos que expõem as funcionalidades do sistema. Desenvolvi:
- Endpoints para CRUD de usuários com controle de permissões (administrador, analista, consultor)
- Endpoints para cadastro, atualização e listagem de áreas agrícolas com validação de GeoJSON
- Endpoints para atribuição de talhes aos analistas e armazenamento de edições
- Endpoints para geração e consulta de dashboards com filtros dinâmicos
- Sistema de rastreamento de tempo desde o cadastro até a aprovação de análises

Implementei tratamento de erros com códigos HTTP apropriados, validação de entrada de dados e respostas padronizadas em JSON.

### Autenticação e Autorização com Spring Security

Implementei um sistema completo de segurança utilizando Spring Security que garante:
- Autenticação de usuários com email e senha
- Controle de acesso baseado em papéis (RBAC - Role Based Access Control)
- Geração de tokens JWT para requisições autenticadas
- Proteção de endpoints sensíveis conforme o papel do usuário
- Logging de todas as atividades críticas (login, alterações de dados, aprovações)

<details>
  <summary>📝 Exemplo: Configuração de Segurança</summary>

```java
@Configuration
@EnableWebSecurity
public class SecurityConfig {
    
    @Autowired
    private UserDetailsService userDetailsService;
    
    @Bean
    public SecurityFilterChain filterChain(HttpSecurity http) throws Exception {
        http
            .csrf().disable()
            .authorizeRequests()
                .antMatchers("/api/auth/**").permitAll()
                .antMatchers("/api/admin/**").hasRole("ADMIN")
                .antMatchers("/api/analista/**").hasRole("ANALISTA")
                .antMatchers("/api/consultor/**").hasAnyRole("CONSULTOR", "ADMIN")
                .anyRequest().authenticated()
            .and()
            .sessionManagement()
                .sessionCreationPolicy(SessionCreationPolicy.STATELESS)
            .and()
            .addFilterBefore(jwtAuthenticationFilter(), UsernamePasswordAuthenticationFilter.class);
        
        return http.build();
    }
    
    @Bean
    public PasswordEncoder passwordEncoder() {
        return new BCryptPasswordEncoder();
    }
    
    @Bean
    public AuthenticationManager authenticationManager(AuthenticationConfiguration config) throws Exception {
        return config.getAuthenticationManager();
    }
}
```

</details>

### Manipulação de Dados Geoespaciais

Implementei funcionalidades complexas para manipular e armazenar dados geoespaciais:
- Parser de arquivos GeoJSON para extração de coordenadas e geometrias
- Armazenamento de geometrias em MySQL utilizando tipos de dados espaciais (GEOMETRY)
- Cálculo de áreas e perímetros de geometrias
- Queries espaciais para filtros por localização geográfica

<details>
  <summary>📝 Exemplo: Serviço de Processamento de GeoJSON</summary>

```java
@Service
public class GeoJsonProcessingService {
    
    @Autowired
    private AreaRepository areaRepository;
    
    public Area processarGeoJSON(File arquivo, AreaDTO areaDTO) throws IOException {
        ObjectMapper mapper = new ObjectMapper();
        JsonNode geoJson = mapper.readTree(arquivo);
        
        Area area = new Area();
        area.setNomeFazenda(areaDTO.getNomeFazenda());
        area.setCultura(areaDTO.getCultura());
        area.setProdutividade(areaDTO.getProdutividade());
        area.setCidade(areaDTO.getCidade());
        area.setEstado(areaDTO.getEstado());
        
        // Extrair geometria do GeoJSON
        String geometryWKT = extrairGeometriaWKT(geoJson);
        area.setGeometria(geometryWKT);
        
        // Calcular área
        double areaKm2 = calcularArea(geoJson);
        area.setAreaKm2(areaKm2);
        
        area.setDataCadastro(LocalDateTime.now());
        area.setStatus("PENDENTE_ANALISE");
        
        return areaRepository.save(area);
    }
    
    private String extrairGeometriaWKT(JsonNode geoJson) {
        JsonNode geometry = geoJson.get("geometry");
        
        if (geometry.get("type").asText().equals("Polygon")) {
            JsonNode coordinates = geometry.get("coordinates").get(0);
            StringBuilder wkt = new StringBuilder("POLYGON((");
            
            for (JsonNode coord : coordinates) {
                wkt.append(coord.get(0).asDouble()).append(" ")
                   .append(coord.get(1).asDouble()).append(",");
            }
            
            wkt.deleteCharAt(wkt.length() - 1);
            wkt.append("))");
            return wkt.toString();
        }
        
        return null;
    }
    
    private double calcularArea(JsonNode geoJson) {
        // Implementação de cálculo de área utilizando biblioteca GIS
        // Exemplo simplificado
        return 0.0; // Retorna área em km²
    }
}
```

</details>

### Interface Frontend com Vue.js

Como responsável pela integração frontend-backend, desenvolvi componentes Vue.js que permitem:
- Visualização interativa de mapas com Leaflet
- Upload de arquivos GeoJSON com validação
- Formulários para cadastro de áreas com campos obrigatórios
- Edição de geometrias com ferramentas de desenho
- Gerenciamento de estado e integração com APIs REST do backend
- Interfaces para aprovação/rejeição de mapas de classificação

<details>
  <summary>📝 Exemplo: Componente de Mapa Interativo</summary>

```vue
<template>
  <div class="map-container">
    <div id="map" ref="mapContainer"></div>
    
    <div class="toolbar">
      <button @click="enableDrawing" class="btn-draw">Desenhar Área</button>
      <button @click="salvarEdicao" class="btn-save">Salvar Edição</button>
      <button @click="cancelarEdicao" class="btn-cancel">Cancelar</button>
    </div>
    
    <div class="info-panel" v-if="areaAtual">
      <h3>{{ areaAtual.nomeFazenda }}</h3>
      <p>Cultura: {{ areaAtual.cultura }}</p>
      <p>Área: {{ areaAtual.areaKm2 }} km²</p>
      <p>Status: {{ areaAtual.status }}</p>
    </div>
  </div>
</template>

<script>
import L from 'leaflet';

export default {
  name: 'MapaInterativo',
  data() {
    return {
      map: null,
      drawControl: null,
      featureGroup: null,
      edicaoAtiva: false
    };
  },
  computed: {
    areaAtual() {
      return this.$store.state.areas.areaAtual;
    }
  },
  mounted() {
    this.inicializarMapa();
    this.carregarAreas();
  },
  methods: {
    inicializarMapa() {
      this.map = L.map(this.$refs.mapContainer).setView([-15.7942, -47.8822], 4);
      
      L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
        attribution: '© OpenStreetMap contributors',
        maxZoom: 19
      }).addTo(this.map);
      
      this.featureGroup = L.featureGroup().addTo(this.map);
    },
    
    enableDrawing() {
      this.edicaoAtiva = true;
    },
    
    salvarEdicao() {
      const geoJSON = this.featureGroup.toGeoJSON();
      this.$store.dispatch('areas/salvarArea', { 
        areaId: this.areaAtual.id, 
        geometria: geoJSON 
      });
    },
    
    cancelarEdicao() {
      this.edicaoAtiva = false;
      this.featureGroup.clearLayers();
    }
  }
};
</script>

<style scoped>
.map-container {
  position: relative;
  width: 100%;
  height: 600px;
}
</style>
```

</details>

### Geração de Dashboards e Rastreamento de Tempo

Implementei uma arquitetura escalável para:
- Agregação de dados por diferentes dimensões (cultura, estado, período)
- Cálculo de métricas de produtividade e análises realizadas
- Rastreamento automático de tempo desde cadastro até aprovação final
- Filtros dinâmicos que atualizam gráficos em tempo real
- Exportação de relatórios consolidados

---

## Aprendizados Efetivos 📚

Este foi um semestre marcante que consolidou minha competência em desenvolvimento full-stack:

### Arquitetura Desacoplada (Frontend/Backend)

Neste semestre, experimentei os benefícios reais de separar repositórios cliente e servidor:
- Desenvolvimento paralelo de equipes especializadas
- Independência de deployment e escalabilidade
- Facilidade de manutenção e evolução independente de cada camada
- Comunicação clara através de APIs bem documentadas

### Sistemas de Informação Geográfica (SIG)

Desenvolvendo com dados geoespaciais, aprendi conceitos importantes:
- Tipos de dados espaciais e operações geométricas
- Formatos como GeoJSON e WKT (Well-Known Text)
- Queries espaciais e índices geográficos
- Visualização de dados em mapas interativos

### Spring Security Avançado

Implementei um sistema robusto de segurança que me ensinou:
- Autenticação baseada em tokens JWT
- Controle de acesso por papéis (RBAC) granular
- Proteção contra ataques comuns
- Logging e auditoria de atividades críticas

### Vue.js em Contexto Real

Trabalhar com Vue.js consolidou meu conhecimento em:
- Desenvolvimento reativo com componentes reutilizáveis
- Gerenciamento de estado com Vuex
- Integração com bibliotecas externas (Leaflet)
- Otimização de performance em aplicações complexas

### Processamento de Imagens e Dados Complexos

O projeto envolveu manipulação de:
- Arquivos GeoJSON e geometrias complexas
- Cálculos geométricos e espaciais
- Agregação de dados para relatórios
- Rastreamento de tempo e métricas de desempenho

### Trabalho em Equipes de Grande Escala

Neste semestre, o projeto envolveu aproximadamente 10 desenvolvedores organizados em especialistas de diferentes áreas. Aprendi:
- Importância de comunicação clara através de APIs bem definidas
- Documentação robusta de endpoints e fluxos
- Code review rigoroso e padrões de código
- Integração contínua e deploy automatizado

---

## Competências Desenvolvidas 🏆

### Hard Skills

| Tecnologia/Metodologia | Proficiência | Classificação |
|------------------------|--------------|---------------|
| Java | ⭐⭐⭐⭐⭐ | Sei fazer com autonomia |
| Spring Boot | ⭐⭐⭐⭐⭐ | Sei fazer com autonomia |
| Spring Security | ⭐⭐⭐⭐☆ | Sei fazer com ajuda |
| Vue.js | ⭐⭐⭐⭐☆ | Sei fazer com ajuda |
| MySQL | ⭐⭐⭐⭐⭐ | Sei fazer com autonomia |
| Dados Geoespaciais (GeoJSON, WKT) | ⭐⭐⭐⭐☆ | Sei fazer com ajuda |
| Leaflet (Mapas Interativos) | ⭐⭐⭐⭐☆ | Sei fazer com ajuda |
| Docker | ⭐⭐⭐⭐☆ | Sei fazer com ajuda |
| APIs REST | ⭐⭐⭐⭐⭐ | Sei fazer com autonomia |
| Git/Versionamento | ⭐⭐⭐⭐⭐ | Sei fazer com autonomia |

### Soft Skills

| Habilidade | Descrição |
|-----------|-----------|
| **Comunicação em Equipes Grandes** | Trabalhei com aproximadamente 10 desenvolvedores, mantendo comunicação clara sobre APIs, dependências e requisitos. |
| **Pensamento Arquitetural** | Participei da definição de arquitetura desacoplada, design de APIs e estrutura do banco de dados. |
| **Resolução de Problemas Complexos** | Implementei soluções complexas envolvendo dados geoespaciais, segurança e integrações entre sistemas. |
| **Independência e Autonomia** | Responsável por features completas do backend, desde design até implementação e testes. |
| **Adaptabilidade** | Aprendi múltiplas tecnologias novas (Spring Security, dados geoespaciais, Vue.js) durante o projeto. |
| **Atenção a Detalhes** | Validação rigorosa de dados, tratamento de erros e segurança foram prioridades constantes. |
| **Gestão de Tempo** | Entrega consistente de features dentro das sprints, mesmo em projetos complexos. |

---

## Como Contribui para o Projeto 🔧

Minha contribuição foi distribuída entre as três sprints:

**Sprint 1**: Implementação de endpoints REST para cadastro de usuários e áreas agrícolas, integração com parser de GeoJSON, validação de dados de entrada e armazenamento em MySQL com tipos de dados espaciais.

**Sprint 2**: Desenvolvimento de endpoints para visualização de talhes, edição de mapas de classificação de IA, comparação de imagens antes/depois, e lógica de aprovação com rastreamento de tempo.

**Sprint 3**: Implementação de endpoints de segurança com Spring Security e JWT, desenvolvimento de APIs para dashboards com filtros dinâmicos, cálculo de métricas de produtividade e sistema completo de logging de atividades.

---

## Reflexão Final 💭

Este foi um ponto de inflexão em minha carreira como desenvolvedor. Trabalhando em um projeto de grande escala com múltiplos especialistas, percebi que desenvolvimento profissional vai muito além de codificação. Aprendi que qualidade e sucesso dependem de:
- **Arquitetura bem pensada**: A separação entre cliente e servidor foi fundamental para nossa escalabilidade
- **Comunicação clara**: APIs bem definidas e documentadas permitiram que equipes trabalhassem independentemente
- **Segurança desde o início**: Spring Security não foi "bolado ao final", mas planejado desde o início
- **Trabalho colaborativo**: Code review, pair programming e discussões técnicas elevaram a qualidade do projeto
- **Dados complexos exigem respeito**: Dados geoespaciais exigem compreensão profunda e atenção a detalhes

Este semestre representou meu crescimento de desenvolvedor iniciante para profissional em formação, pronto para desafios ainda maiores.

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
    <td><a href="https://github.com/pablohgs05/PortfolioBD-Pablo/blob/main/API_6.md">API 6</a></td>
  </tr>
</table>

</div>
