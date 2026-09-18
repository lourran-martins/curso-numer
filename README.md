# Documentação Normativa e Termos de Uso: Curso & Numeração Offline

Autor e Desenvolvedor Principal: Lourran Martins Fonseca
Localidade: Cachoeiras de Macacu, RJ, Brasil
Licenciamento: Apache License 2.0
Classificação do Software: CAQDAS (Computer-Assisted Qualitative Data Analysis Software) e RAG (Retrieval-Augmented Generation) Progressivo.

1. Natureza e Escopo do Software

O Curso & Numeração é uma Aplicação Web Progressiva (PWA) projetada para a análise qualitativa sistêmica de grandes volumes de dados textuais e planilhas. A arquitetura foi concebida sob o paradigma Offline-First, garantindo que pesquisadores, agentes governamentais e analistas de dados possam processar fontes primárias, codificar variáveis e estabelecer cruzamentos matriciais sem a necessidade de infraestrutura de rede ativa ou servidores externos.

A plataforma consolida as seguintes esferas de atuação:

Gestão de Corpus: Leitura e indexação local de arquivos em múltiplos formatos (.txt, .csv, .xlsx, .md, .json, .html).

Engenharia Qualitativa: Criação de árvores de Códigos (Nós) e atributos de Casos (Consolidações Cotidianas).

Análise Estatística e Heurística: Geração de Matrizes de coocorrência, cálculo de Equação de Compatibilidade de Jaccard e Super Análise Textual tridimensional.

Inteligência Artificial (Módulo IA): Integração Serverless com a API do OpenRouter, operando mediante RAG (Busca e Geração Aumentada) estritamente local, com renderização de diagramas dinâmicos.

2. Política de Privacidade e Tratamento de Dados (Compliance)

A arquitetura do aplicativo foi desenhada para assegurar a inviolabilidade dos dados de pesquisa, operando de maneira descentralizada no dispositivo do próprio usuário.

2.1. Armazenamento e Criptografia Local

Isolamento de Dados: Nenhum arquivo de pesquisa, nota metodológica, atributo de participante ou livro de códigos é enviado para bancos de dados de terceiros de forma oculta. O armazenamento ocorre integralmente no banco de dados local do navegador do usuário (IndexedDB, sob a base curso_numeracao_offline_v3).

Camada de Proteção Intradispositivo: O acesso ao aplicativo e à leitura do IndexedDB é protegido por uma interface de criptografia inicial. O sistema exige a criação de uma senha de acesso cujos caracteres são convertidos em um hash irreversível (cn_crypto_hash), impedindo que usuários não autorizados no mesmo dispositivo físico acessem os dados consolidados.

2.2. Operação do Módulo de Inteligência Artificial (LLM)

A integração com o modelo de linguagem ocorre sob os mais estritos padrões de controle de fluxo de dados, exigindo consentimento explícito.

Chave de API Privada (BYOK - Bring Your Own Key): O aplicativo não fornece chaves globais. O usuário deve gerar sua credencial (AIzaSy...) diretamente no OpenRouter e inseri-la na plataforma. A chave permanece armazenada apenas na memória local do aparelho.

Filtragem Semântica Local (RAG): Para proteger o sigilo das fontes brutas e otimizar limites de pacotes de dados, o aplicativo não envia o corpus integral para a nuvem. O algoritmo de Inteligência Qualitativa fragmenta os textos offline, isola os parágrafos relevantes à pergunta formulada, exclui termos de descarte (Stopwords) e envia unicamente a amostragem cirúrgica consolidada para a API.

Consentimento Obrigatório: O botão de disparo para a nuvem permanece desabilitado por padrão. O envio do payload analítico (JSON otimizado) para os servidores do Google (via POST HTTP) exige marcação manual de aceite pelo usuário a cada nova bateria de inferências.

3. Termos de Uso e Responsabilidade

Ao utilizar o Curso & Numeração, o usuário concorda com os seguintes preceitos metodológicos e operacionais:

Responsabilidade sobre Backups: Por ser uma ferramenta estritamente local que depende do cache do navegador (sw.js e IndexedDB), o pesquisador é o único responsável pela integridade a longo prazo dos seus dados. É imperativo o uso rotineiro do botão "Exportar Relatório Final PDF + JSON" para garantir salvaguardas externas.

Uso de Limites de API: A comunicação do módulo de IA depende da cota de requisições por minuto (RPM) e tokens por minuto (TPM) vinculada à conta Google do usuário. Erros de status por saturação (como Status 503 - High Demand) independem da plataforma e derivam da política comercial da provedora da infraestrutura do LLM.

Natureza Probabilística da IA: O Analista de Inteligência Qualitativa foi parametrizado com baixa variância criativa (Temperature: 0.2) para agir com rigor metodológico; no entanto, relatórios gerados por modelos fundacionais possuem natureza probabilística. As deduções, resumos automáticos e diagramas extraídos devem passar por revisão hermenêutica humana antes de endossarem tomadas de decisão ou documentação oficial.

4. Arquitetura e Especificações Técnicas

O aplicativo consolida tecnologias modernas para dispensar a necessidade de terminais intermédios ou servidores Node.js em localhost.

Front-end: Código estruturado em HTML5, CSS nativo com variáveis CSS para controle de tema (Claro/Escuro) e JavaScript Vanilla (ECMAScript 6+).

Persistência de Dados: IndexedDB API nativa do W3C.

Capacidade Offline: Gerenciada por um Service Worker (sw.js) e mapeamento PWA via manifest.json.

Bibliotecas e Dependências Externas (via CDN):

SheetJS (xlsx.full.min.js): Conversão local e análise quantitativa de planilhas e matrizes de colunas múltiplas.

Chart.js: Renderização nativa de gráficos de pizza, linha e barra (ranqueamentos e super análise).

HTML2PDF (html2pdf.bundle.min.js): Consolidação de relatórios hipercompletos encapsulados em PDF gerado diretamente do DOM.

Marked.js: Renderização acadêmica de formatação tipográfica e tabelas via Markdown.

Mermaid.js: Motor analítico para converter saídas do LLM em gráficos e organogramas visuais em tempo real.

5. Disposições de Licença

O código-fonte base, a estruturação de layout e os motores de cruzamento semântico offline operam sob a Licença Apache 2.0. O uso para pesquisas acadêmicas, sindicâncias, análises de dados governamentais e uso comercial é permitido, resguardando a isenção de responsabilidades do autor e a impossibilidade de imputação de ônus derivados da perda de dados locais ou mau uso de integrações de rede.

