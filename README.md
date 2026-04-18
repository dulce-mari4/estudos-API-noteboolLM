# Caderno Temático: Construções e Boas Práticas em APIs

Abaixo, apresento o ambiente de estudo configurado no NotebookLM, onde realizei a curadoria de 16 fontes técnicas e utilizei engenharia de prompts para consolidar os conceitos de arquitetura REST.

![Interface de estudo evidenciando a curadoria de fontes como Netflix TechBlog e OpenAPI.](https://github.com/dulce-mari4/estudos-API-noteboolLM/blob/main/NotebookLM%20API.png)

---

## Contexto e Objetivos
Este repositório é o resultado de um estudo aprofundado sobre a arquitetura de comunicação entre sistemas. Como estudante de Ciência da Computação, identifiquei a necessidade de evoluir meu entendimento sobre APIs (Application Programming Interfaces), indo além do uso superficial e mergulhando nos conceitos de escalabilidade e design arquitetural.
Objetivo Principal: Superar a barreira teórica sobre o estilo REST e compreender como aplicar suas restrições de forma prática (RESTful), utilizando o NotebookLM como ferramenta de síntese e troubleshooting de conhecimento.

---

## Curadoria de Fontes
Utilizei as seguintes fontes fundamentais para alimentar a base de conhecimento da IA:

[Richardson Maturity Model](https://martinfowler.com/articles/richardsonMaturityModel.html) - Martin Fowler: O framework para medir a maturidade de uma API.

[Microsoft REST API Design Best Practices](https://learn.microsoft.com/en-us/azure/architecture/best-practices/api-design): Guia prático de padrões de mercado.

[OWASP API Security Top 10](https://owasp.org/www-project-api-security/): Referência essencial para segurança e proteção de dados.

[OpenAPI Specification (Swagger)](https://swagger.io/specification/): Documentação do padrão de descrição de contratos.

As fontes listadas foram utilizadas estritamente para fins de estudo pessoal e extração de conhecimento via NotebookLM, respeitando as diretrizes de uso acadêmico de cada autor.

---

## Engenharia de Prompts e "Cicatrizes" (Troubleshooting)
A Evolução do Pensamento
Para extrair o melhor da IA, não fiz perguntas genéricas. Testei variações para garantir que a resposta não fosse apenas "o que é", mas "como funciona sob a ótica da computação".

### Prompt Inicial: "O que é uma API REST?"
Resultado: Resposta genérica sobre JSON e HTTP.
### Prompt Estratégico: "Você é um especialista em arquitetura. Diferencie REST (teoria) de RESTful (prática) usando analogias de protocolos de rede e persistência."
Raciocínio: Ao forçar a IA a usar analogias de baixo nível (OSI, Schemas), consegui uma explicação que conecta a API com os fundamentos que estudo na faculdade.
Dificuldade Encontrada: Inicialmente, a IA confundia REST com o protocolo HTTP. Tive que iterar perguntando: "É possível ter REST sem HTTP?". Isso ajudou a separar o estilo arquitetural do meio de transporte.

---

## Miniguia de Estudo

### 1. Resumo Estruturado: O Coração do REST
Uma API não é algo material, mas sim um contrato de abstração. O modelo ideal segue o Design "Outside-in" (focado no consumidor).

### 2. Glossário de Conceitos Chave
Stateless: O servidor não guarda memória do estado do cliente. Cada requisição é única.
Idempotência: A garantia de que realizar a mesma operação várias vezes (como um GET ou PUT) terá o mesmo efeito.
HATEOAS: O nível máximo de maturidade; a API te diz para onde ir através de links na resposta.
Endpoint: A URL que representa um recurso (ex: /clientes).

### 3. Prompts Reutilizáveis para Revisão
"Explique o conceito de idempotência nos verbos HTTP PUT e PATCH com exemplos de código."
"Analise o seguinte endpoint POST /get_all_users sob a ótica do Modelo de Maturidade de Richardson." (Dica: Esse endpoint fere o nível 2!).

### 4. Glossário de Conceitos Fundamentais

4.1. Abstração e Contrato
API (Application Programming Interface): Não é um código físico, mas um contrato. É a definição de como um componente de software interage com outro, escondendo a complexidade da implementação interna (encapsulamento).

Interface Uniforme: É a restrição do REST que exige que a comunicação seja padronizada. Se todos usarem os mesmos métodos (GET, POST, etc) e identificadores (URIs), o sistema se torna previsível e escalável.

4.2. O Estilo RESTful
Stateless (Sem Estado): Uma das restrições mais importantes. Significa que o servidor não guarda nenhuma informação sobre o cliente entre uma requisição e outra. Cada chamada deve ser "autossuficiente", contendo todos os dados necessários (como tokens de autenticação).

Recurso (Resource): No REST, tudo é um recurso. Um cliente, um pedido ou uma foto são recursos identificados por uma URI (Uniform Resource Identifier).

HATEOAS (Hypermedia as the Engine of Application State): O nível mais alto de maturidade (Nível 3 de Richardson). A API retorna links que dizem ao cliente quais são as próximas ações possíveis, como um menu de navegação em um site.

4.3. Verbos e Semântica HTTP
Idempotência: Propriedade de alguns métodos HTTP (como GET, PUT e DELETE) onde realizar a mesma operação múltiplas vezes produz o mesmo resultado final no servidor. É vital para a tolerância a falhas em sistemas distribuídos.

Safe Methods (Métodos Seguros): Métodos que não alteram o estado do servidor, como o GET. Eles podem ser cacheados livremente para melhorar a performance.

4.4. Payload e Representação
JSON (JavaScript Object Notation): O formato de representação mais comum para APIs RESTful por ser leve e fácil de ler tanto por humanos quanto por máquinas.

Payload: É o "corpo" da mensagem enviada em uma requisição (geralmente no POST ou PUT), contendo os dados que serão processados pelo servidor.

## Conclusão
Ao final deste projeto, percebi que a maior dificuldade não era o código em si, mas entender que o REST é uma filosofia de design. Usar o NotebookLM para confrontar a teoria acadêmica (Fielding) com a prática de mercado (Microsoft) me permitiu construir uma base sólida para desenvolver APIs que não apenas funcionam, mas são resilientes e escaláveis.
