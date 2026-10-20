CLAUDE.md

UrbsGPS

Visão Geral
Projeto: UrbsGPS

Tipo: Build to Learn

Data de início: 19/10/2026

Objetivo
O UrbsGPS tem como objetivo democratizar e otimizar o uso do transporte público por meio de uma experiência mobile simples e acessível.

O sistema reduz a incerteza dos usuários nos pontos de ônibus e melhora a eficiência operacional do transporte ao facilitar o embarque correto, reduzir erros de trajeto e agilizar a tomada de decisão de passageiros e motoristas.

Problema que Resolve
Muitos usuários não sabem:

- Quais ônibus passam em determinado ponto;
- Quais rotas cada linha realiza;
- Qual linha escolher para chegar ao destino desejado;
- Quais opções de ida e volta existem a partir de um ponto específico.
- O UrbsGPS resolve esse problema utilizando QR Codes físicos associados a pontos de ônibus.

Funcionamento
O usuário abre o aplicativo.
Escaneia o QR Code do ponto de ônibus.
O aplicativo identifica o ponto correspondente.
Carrega informações daquela localização.
Exibe:
Linhas de ônibus disponíveis;
Rotas das linhas;
Informações relevantes para embarque;
Opções para ida e retorno.
O usuário escolhe a linha desejada.
A experiência de embarque torna-se mais rápida e intuitiva.

Responsáveis

Decisões de Produto
Daniel Biehl Stiwers
Otto Miguel de Moraes

Aprovação e Validação
Toda decisão arquitetural, funcional ou de negócio deve ser validada por:

Daniel Biehl Stiwers
Otto Miguel de Moraes

Arquitetura
Modelo de Repositório
Monorepo

Estrutura sugerida:

urbsgps/
├── apps/
│   └── mobile/
├── services/
│   └── backend/
├── database/
├── infrastructure/
├── docs/
└── CLAUDE.md

Stack Tecnológica

Frontend
Kotlin + Jetpack Compose

Motivação:
Excelente performance mobile;
Integração nativa com Android;
Segurança de tipos;
Produtividade elevada.

Backend
Java Spring Boot

Motivação:
Ecossistema consolidado;
Ampla adoção corporativa;
Robustez para APIs e regras de negócio;
Boa manutenção de longo prazo.

Banco de Dados
PostgreSQL + PostGIS

Motivação:
Estrutura relacional adequada;
Integridade dos dados;
Excelente suporte a consultas geográficas;
Forte confiabilidade para aplicações transacionais.

APIs Externas

Google Maps
Utilizado para:
Geolocalização;
Visualização de rotas;
Navegação;
Mapas.

Google Storage
Utilizado para:
Armazenamento de arquivos;
Assets estáticos;
Possíveis recursos multimídia.

Testes de API:
- Insomnia
- Swagger/OpenAPI

Infraestrutura
Containerização
Docker

Todos os serviços devem possuir ambiente isolado e reproduzível por containers.

Objetivos:

Padronização do ambiente;
Facilidade de onboarding;
Redução de problemas de compatibilidade;
Deploy consistente.

Framework de Desenvolvimento
XP (Extreme Programming)
O projeto seguirá os princípios de XP:

Simplicidade
Feedback rápido
Comunicação
Coragem
Respeito
Práticas recomendadas:

Desenvolvimento incremental;
Refatoração contínua;
Testes automatizados;
Integração frequente;
Revisão constante do código;
Entregas pequenas e frequentes.

Regras Obrigatórias para Agentes e Desenvolvedores

1. Ler Antes de Alterar
Antes de implementar qualquer mudança:

Ler a documentação existente.
Ler a arquitetura atual.
Entender fluxos afetados.
Identificar impactos técnicos.
Verificar decisões registradas anteriormente.
Nenhuma alteração deve ser realizada sem entendimento prévio do contexto.

2. Executar Verificações Antes de Codificar
Antes de criar ou modificar código, executar e validar:

Testes
# executar todos os testes
Lint
# executar lint do projeto
Build
# validar build completo
Migrações
# validar migrações pendentes
Features Existentes
Verificar que:

Funcionalidades atuais continuam funcionando;
Não houve regressão;
Integrações permanecem estáveis.
3. Qualidade de Código
Toda implementação deve:

Seguir SOLID;
Seguir Clean Code;
Evitar duplicação;
Manter simplicidade;
Priorizar legibilidade;
Possuir tratamento adequado de erros;
Incluir testes quando aplicável.
4. Documentação de Variáveis de Ambiente
Toda variável de ambiente criada deve ser documentada.

Formato obrigatório:

Variável	Finalidade	Obrigatória	Exemplo
DATABASE_URL	Conexão com PostgreSQL	Sim	postgres://...
GOOGLE_MAPS_API_KEY	Integração Google Maps	Sim	xxxx
GOOGLE_STORAGE_BUCKET	Bucket principal	Sim	urbsgps-prod
Nenhuma variável pode existir sem documentação correspondente.

5. Atualização da Documentação
Este arquivo deve ser atualizado sempre que houver:

Mudanças arquiteturais;
Novas integrações;
Novas regras de negócio;
Alterações de processo;
Mudanças de stack;
Decisões técnicas relevantes.
A documentação deve representar o estado atual do sistema.

6. Segurança Operacional
É obrigatório solicitar confirmação humana antes de:

Ações destrutivas
Exemplos:

DROP DATABASE
DELETE em massa
Limpeza de storage
Remoção de tabelas
Exclusão de buckets
Deploys
Exemplos:

Produção
Homologação
Ambientes compartilhados
Operações com Dados Reais
Exemplos:

Migração de produção
Alterações massivas
Backfills
Importações
Exportações
7. Versionamento Seguro
Antes de qualquer alteração significativa:

Confirmar existência de Git.
Confirmar existência de backup.
Confirmar possibilidade de rollback.
Trabalhar em branch dedicada.
Fluxo recomendado:

main
 ├─ develop
 └─ feature/nome-da-feature
Nunca trabalhar diretamente na branch principal.

8. Processo de Desenvolvimento
Fluxo recomendado:

Ler documentação.
Entender contexto.
Executar testes.
Executar lint.
Validar build.
Verificar migrações.
Implementar alteração.
Criar testes.
Executar testes novamente.
Atualizar documentação.
Abrir revisão.
9. Registro de Decisões
Mudanças relevantes devem gerar registro contendo:

Contexto
Problema
Alternativas avaliadas
Decisão escolhida
Justificativa
Impactos
Sugestão:

docs/adr/
Utilizar ADRs (Architecture Decision Records).

Diretrizes para IA
Ao atuar neste projeto, o agente deve:

Ler primeiro este arquivo.
Ler documentação relacionada ao contexto.
Preservar compatibilidade.
Minimizar mudanças desnecessárias.
Não alterar comportamento existente sem justificativa.
Atualizar documentação afetada.
Priorizar simplicidade.
Validar impacto antes de modificar componentes compartilhados.
Solicitar confirmação humana para operações críticas.
Visão de Futuro
Possíveis expansões:

Tempo real dos ônibus;
Integração com GPS das frotas;
Planejador de viagens;
Alertas de chegada;
Rotas acessíveis;
Integração com múltiplas cidades;
Histórico de deslocamentos;
Analytics para órgãos públicos.
Status do Projeto
Fase atual:

Planejamento e aprendizado (Build to Learn)

Objetivo principal:

Validar a proposta, aprender tecnologias envolvidas e construir uma solução funcional focada na experiência do usuário do transporte público.

Estratégia de Desenvolvimento
Backend First
O projeto seguirá a abordagem Backend First.

Antes da implementação de qualquer interface visual, as funcionalidades deverão existir e estar validadas na API.

Fluxo obrigatório:

Modelar os dados.
Implementar regras de negócio.
Implementar endpoints da API.
Criar ou atualizar documentação da API.
Executar testes automatizados.
Validar endpoints no Insomnia.
Executar lint.
Executar build.
Validar migrações.
Somente após a aprovação da API iniciar a implementação do frontend.
Critério de Pronto para Backend
Uma funcionalidade somente poderá ser considerada pronta para integração com o frontend quando:

Todas as regras de negócio estiverem implementadas;
Os endpoints estiverem documentados;
Os testes estiverem passando;
O build estiver válido;
As migrações estiverem aplicadas e testadas;
A funcionalidade tiver sido validada manualmente pelo Insomnia.
Responsabilidade do Frontend
O frontend não deve conter regras de negócio críticas.

Responsabilidades do aplicativo:

Escaneamento de QR Code;
Exibição de informações;
Navegação entre telas;
Comunicação com APIs;
Geolocalização e mapas;
Experiência do usuário.
Responsabilidades do backend:

Processamento de dados;
Regras de negócio;
Segurança;
Validação de dados;
Controle de acesso;
Integrações externas;
Persistência de dados.
Fluxo de Desenvolvimento de Features
Para cada nova funcionalidade:

Criar ou atualizar modelagem.
Implementar backend.
Criar testes.
Validar via Insomnia.
Revisar documentação.
Atualizar OpenAPI/Swagger.
Atualizar CLAUDE.md se necessário.
Implementar frontend consumindo a API já validada.
Realizar testes de integração.
Abrir revisão para aprovação.
Ferramentas Oficiais
Backend:

Java
Spring Boot
PostgreSQL
Docker
Validação da API:

Insomnia
Swagger/OpenAPI
Frontend:

Kotlin
Jetpack Compose
A regra do projeto é:

Nenhuma tela deve ser criada para uma funcionalidade cuja API ainda não tenha sido implementada, documentada e validada no Insomnia.

Política de Versionamento
Objetivo
Garantir rastreabilidade, segurança, rollback e evolução controlada do sistema.

Todo código, banco de dados, API e documentação devem seguir as políticas descritas nesta seção.

Controle de Versão
O projeto utiliza Git como sistema oficial de versionamento.

Nenhuma alteração deve ser realizada sem que exista histórico rastreável.

É obrigatório:

Utilizar Git.
Possuir repositório remoto configurado.
Trabalhar em branches dedicadas.
Possuir possibilidade de rollback.
Realizar commits frequentes e descritivos.
Estratégia de Branches
Branches permanentes:

main
develop
Main
Branch estável do sistema.

Regras:

Não receber commits diretos.
Deve conter apenas código validado.
Deve ser protegida.
Develop
Branch principal de desenvolvimento.

Responsável por integrar funcionalidades antes de chegarem à main.

Feature Branches
Toda nova funcionalidade deve ser criada a partir da develop.

Padrão:

feature/nome-da-feature
Exemplos:

feature/qr-code-reader
feature/bus-routes
feature/google-maps
feature/bus-stop-search
Fix Branches
Correções de bugs.

Padrão:

fix/nome-do-problema
Exemplos:

fix/null-pointer-route-service
fix/qr-scan-crash
Hotfix Branches
Correções urgentes em produção.

Padrão:

hotfix/nome-do-problema
Conventional Commits
Todos os commits devem seguir o padrão Conventional Commits.

Tipos permitidos:

feat
fix
docs
test
refactor
chore
perf
build
ci
Exemplos:

feat: adiciona leitura de QR Code

fix: corrige busca de linhas por ponto

docs: atualiza CLAUDE.md

test: adiciona testes da API de rotas

refactor: reorganiza camada de serviços

chore: atualiza dependências
Commits devem descrever claramente a alteração realizada.

Semantic Versioning (SemVer)
O projeto utiliza Semantic Versioning.

Formato:

MAJOR.MINOR.PATCH
Exemplo:

1.0.0
PATCH
Correções sem alteração de comportamento público.

Exemplo:

1.0.0 → 1.0.1
MINOR
Novas funcionalidades compatíveis.

Exemplo:

1.0.0 → 1.1.0
MAJOR
Mudanças incompatíveis com versões anteriores.

Exemplo:

1.9.0 → 2.0.0
Tags de Release
Toda versão publicada deve receber uma tag Git.

Exemplos:

git tag v0.1.0
git tag v0.2.0
git tag v1.0.0
Formato obrigatório:

vMAJOR.MINOR.PATCH
Changelog
Toda release deve possuir registro em:

docs/CHANGELOG.md
Modelo:

## [1.0.0]

### Adicionado

- Funcionalidade X

### Alterado

- Funcionalidade Y

### Corrigido

- Problema Z
Versionamento da API
Toda API deve possuir prefixo de versão.

Exemplo:

/api/v1/stops

/api/v1/routes

/api/v1/lines
Mudanças incompatíveis exigem criação de nova versão:

/api/v2/stops
Não quebrar consumidores existentes sem aprovação explícita dos responsáveis do projeto.

Versionamento de Banco de Dados
Toda alteração estrutural deve ocorrer através de migrações.

Exemplo:

V1__initial_schema.sql
V2__create_bus_stops.sql
V3__create_routes.sql
V4__create_qr_codes.sql
Regras:

Nunca alterar migrations já executadas.
Sempre criar uma nova migration.
Toda migration deve ser testada.
Toda migration deve possuir rollback documentado quando aplicável.
Versionamento da Documentação
Alterações significativas em:

Arquitetura;
Regras de negócio;
Fluxos;
Integrações;
Infraestrutura;
devem resultar em atualização da documentação correspondente.

Obrigatório atualizar:

CLAUDE.md
ADRs
CHANGELOG
Documentação técnica impactada
Aprovação para Releases
Antes de publicar uma nova versão:

- Todos os testes devem estar passando.
- Build deve ser válido.
- Migrações devem ser validadas.
- API deve ser validada no Insomnia.
- Documentação deve estar atualizada.
- Mudanças devem estar registradas no CHANGELOG.


Responsáveis pela Aprovação

Aprovação final de releases, mudanças arquiteturais relevantes e mudanças de versionamento:

- Daniel Biehl Stiwers
- Otto Miguel de Moraes

Segurança
Princípios Gerais
Segurança deve ser considerada desde o início do desenvolvimento.

Toda implementação deve seguir o princípio do menor privilégio e exposição mínima de dados.

Segredos e Credenciais
É proibido:

Comitar senhas.
Comitar tokens.
Comitar chaves de API.
Comitar credenciais de banco de dados.
Comitar arquivos .env.
Compartilhar credenciais em documentação.
Obrigatório:

Utilizar variáveis de ambiente.
Documentar todas as variáveis utilizadas.
Utilizar exemplos fictícios em documentação.
Exemplo:

GOOGLE_MAPS_API_KEY=
DATABASE_URL=
JWT_SECRET=
Validação de Entrada
Toda entrada recebida deve ser validada.

Exemplos:

Body de requisições.
Query Parameters.
Path Parameters.
Uploads.
Dados recebidos de APIs externas.
Nenhum dado recebido deve ser considerado confiável por padrão.

Tratamento de Dados Sensíveis
Não registrar em logs:

Senhas.
Tokens.
Chaves de API.
Dados pessoais sensíveis.
Quando necessário, mascarar informações críticas.

Produção
Obrigatório:

HTTPS.
Variáveis de ambiente seguras.
Controle de acesso.
Logs de auditoria para eventos críticos.
Convenções de API
Padrão Geral
Todos os endpoints devem seguir convenções REST.

Padrão de versionamento:

/api/v1
Exemplos:

GET    /api/v1/stops
GET    /api/v1/stops/{id}

POST   /api/v1/stops

PUT    /api/v1/stops/{id}

DELETE /api/v1/stops/{id}
Convenções de URL
Utilizar:

Substantivos no plural.
Letras minúsculas.
Separação por hífen quando necessário.
Exemplos:

/api/v1/bus-stops
/api/v1/routes
/api/v1/bus-lines
Evitar:

/api/v1/getBusStop
/api/v1/busStop
Formato de Resposta
Todas as respostas devem utilizar JSON.

Exemplo:

{
  "id": "123",
  "name": "Terminal Central"
}
Códigos HTTP
Utilizar códigos apropriados.

Exemplos:

200 OK
201 Created
204 No Content

400 Bad Request
401 Unauthorized
403 Forbidden
404 Not Found

409 Conflict

500 Internal Server Error
Documentação
Toda API deve possuir documentação atualizada via:

OpenAPI
Swagger
Mudanças em endpoints exigem atualização da documentação.

Arquitetura Backend
Estrutura de Camadas
O backend deve seguir separação clara de responsabilidades.

Estrutura recomendada:

backend/

├── controller
├── service
├── repository
├── entity
├── dto
├── mapper
├── exception
├── config
└── validation
Fluxo de Responsabilidades
Controller
    ↓
Service
    ↓
Repository
    ↓
PostgreSQL
Controller
Responsável por:

Receber requisições.
Validar entrada.
Retornar respostas HTTP.
Não deve conter regras de negócio.

Service
Responsável por:

Regras de negócio.
Processamento.
Orquestração dos componentes.
Toda lógica de domínio deve permanecer nesta camada.

Repository
Responsável por:

Comunicação com o banco de dados.
Persistência.
Consultas.
Não deve conter regras de negócio.

DTOs
Devem ser utilizados para:

Entrada de dados.
Saída de dados.
Isolamento das entidades de persistência.
Não expor entidades diretamente pela API.

Exceptions
Erros devem ser tratados de forma centralizada.

Objetivos:

Padronizar respostas.
Melhorar rastreabilidade.
Evitar vazamento de detalhes internos.
Dependências Entre Camadas
Permitido:

Controller → Service

Service → Repository
Não permitido:

Controller → Repository

Repository → Controller

Entity → Controller
Evolução Arquitetural
Toda alteração estrutural significativa deve:

Ser documentada.
Gerar ADR quando necessário.
Atualizar este CLAUDE.md.

1. Preparar os dados de transporte
Comece cadastrando pontos, linhas, trajetos, horários e viagens no backend. Uma boa opção é usar o padrão GTFS, comum em dados de transporte público. Ele organiza os dados estáticos; o GTFS-Realtime pode trazer posições dos veículos, previsões de chegada e alertas de serviço.

O PostgreSQL/PostGIS pode armazenar pontos e trajetos geográficos. Antes de escolher o formato definitivo e as fontes de dados, a decisão deve ser validada pelos responsáveis do projeto.

2. GPS da frota e ônibus em tempo real
O GPS é a fonte de localização; “ônibus em tempo real” é o recurso que usa essa localização para mostrar onde os veículos estão e estimar quando chegarão.

Para isso, é preciso obter posições dos ônibus, por exemplo, de dispositivos instalados na frota ou de uma API da empresa de transporte. O backend recebe essas posições, associa cada veículo à linha ou viagem e publica os dados para o aplicativo. A atualização pode ocorrer em intervalos curtos, sem exigir que o celular consulte o servidor continuamente.

Sem acesso a dados reais da frota, é possível desenvolver com dados simulados, mas eles devem aparecer claramente como demonstração, não como informação real.

3. Planejamento de viagens
A pessoa informa origem e destino; a API calcula opções de trajeto, incluindo caminhada até os pontos, linhas a embarcar, possíveis transferências e caminhada final. O backend deve fazer os cálculos, enquanto o app apresenta as alternativas.

Uma primeira versão pode usar pontos, trajetos e horários cadastrados. Depois, pode considerar atrasos e posições reais dos ônibus. Critérios como menor duração, menos transferências ou menos caminhada são decisões de produto que precisam ser definidas.

4. Alertas de chegada
Com as previsões de chegada, o usuário pode pedir um aviso para uma linha ou ponto, como “avise quando o ônibus estiver próximo”. O backend acompanha a condição e envia uma notificação push ao celular.

Para funcionar, será necessário cadastrar a preferência do usuário, integrar um serviço de notificações e definir o que significa “próximo” — uma quantidade em distância. O alerta deve indicar quando a previsão estiver indisponível ou incerta.

5. Rotas acessíveis
O sistema precisa conhecer características dos pontos e trajetos, como acessibilidade do ponto, presença de rampas ou elevadores e acessibilidade dos veículos. Essas informações podem vir da empresa de transporte, de dados públicos ou de levantamentos próprios.

Com os dados disponíveis, o planejador pode filtrar ou priorizar opções acessíveis. É importante não prometer uma rota acessível quando faltarem dados: nesse caso, o app deve informar que a acessibilidade não foi confirmada.

6. Histórico de deslocamentos e rotas favoritas
O histórico pode registrar viagens planejadas ou iniciadas, e os favoritos podem guardar pontos, linhas ou trajetos. Para persistir isso entre dispositivos, o backend precisará associar esses dados a uma conta. Se não houver login, dá para começar armazenando-os somente no aparelho, com menos recursos de sincronização.

Como são dados que podem revelar hábitos e deslocamentos, o histórico deve ser opcional, protegido e acompanhado de controles para consultar e apagar os registros. A política de retenção e a necessidade de conta também devem ser aprovadas antes da implementação.

Ordem sugerida

Organizar pontos, linhas, trajetos e horários.
Criar e validar a API de planejamento básico.
Integrar uma fonte de GPS e exibir posições reais, se disponível.
Usar essas posições para estimar chegadas.
Criar alertas de chegada.
Acrescentar dados e filtros de acessibilidade.
Implementar favoritos e histórico, definindo antes como serão tratados conta, privacidade e exclusão.
Para cada etapa: modelar os dados, implementar as regras e endpoints no backend, documentar com OpenAPI, criar testes e validar no Insomnia. Depois dessa validação, o aplicativo pode consumir a API.