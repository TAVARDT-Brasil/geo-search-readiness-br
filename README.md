<p align="center">
  <a href="https://ag.tavardt.com/br/">
    <img src="https://ag.tavardt.com/img/tavardt-banner.png" alt="TAVARDT" width="1024" />
  </a>
</p>

# Auditor de Otimização para Motores Generativos (GEO)

[![Auditor GEO](https://img.shields.io/badge/TAVARDT-Busca%20IA%20GEO-5b3cf5.svg)](https://tools.tavardt.com/br/auditor-busca-ia-geo/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Mecanismo automatizado de diagnóstico para Generative Engine Optimization (GEO) e Answer Engine Optimization (AEO), auditando acesso de rastreadores de IA, dados estruturados Schema.org e sinais de citação semântica.

A ferramenta avalia propriedades web perante esteiras de geração aumentada por recuperação (RAG) que operam em sistemas como SearchGPT, Perplexity AI, Claude, Gemini e Apple Intelligence. Desenvolvido sem dependências externas, executa nativamente em terminal Python e esteiras de validação contínua.

***

## Capacidades de Verificação GEO e Escopo Algorítmico

A busca tradicional concentrava-se em correspondência de palavras-chave e volume de links. Mecanismos generativos sintetizam respostas conversacionais executando recuperação neural de passagens sobre grafos de conhecimento estruturados e fontes de alta autoridade.

* **Inspeção de Rastreadores de IA**: Verificação minuciosa de diretivas no `robots.txt` para os principais agentes autônomos: GPTBot, OAI-SearchBot, PerplexityBot, ClaudeBot, Google-Extended e Applebot-Extended.
* **Extração de Entidades Estruturadas**: Validação da presença de dados Schema.org em formato JSON-LD (`application/ld+json`), permitindo que LLMs contextualizem fatos e identifiquem entidades corporativas.
* **Hierarquia Semântica e Âncoras Contextuais**: Checagem de títulos H1 e completude de meta descriptions para segmentação precisa de passagens textuais.
* **Pontuação Quantitativa de Prontidão GEO**: Índice algorítmico de 0 a 100 pontos classificando o domínio em Alta Visibilidade, Visibilidade Moderada ou Acesso Restrito.
* **Execução Rápida sem Dependências**: Implementação estrita com bibliotecas nativas do Python, assegurando resposta imediata e total compatibilidade em servidores fechados.

***

## Matriz de Verificação e Pontuação GEO

<table>
  <thead>
    <tr>
      <th align="left">Dimensão Auditada</th>
      <th align="left">Peso da Pontuação</th>
      <th align="left">Regra de Validação Algorítmica</th>
      <th align="left">Impacto na Síntese e Citação de IA</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Disponibilidade do robots.txt</strong></td>
      <td>20 Pontos</td>
      <td>Resposta HTTP 200 válida no endpoint /robots.txt.</td>
      <td>Garante que agentes de busca consigam ler deterministicamente as instruções de indexação.</td>
    </tr>
    <tr>
      <td><strong>Permissões de Bots de IA</strong></td>
      <td>30 Pontos</td>
      <td>Ausência de diretivas Disallow: / bloqueando rastreadores de IA.</td>
      <td>Evita o bloqueio total do domínio nas esteiras de recuperação e citação de LLMs.</td>
    </tr>
    <tr>
      <td><strong>Schema.org JSON-LD</strong></td>
      <td>30 Pontos</td>
      <td>Presença de scripts application/ld+json válidos no código.</td>
      <td>Fornece ancoragem confiável de entidades e mapeamento direto no grafo de conhecimento.</td>
    </tr>
    <tr>
      <td><strong>Meta Description Textual</strong></td>
      <td>10 Pontos</td>
      <td>Tag meta name=description preenchida no cabeçalho do documento.</td>
      <td>Oferece resumo temático inicial para contextualização rápida de respostas e snippets.</td>
    </tr>
    <tr>
      <td><strong>Título Semântico H1</strong></td>
      <td>10 Pontos</td>
      <td>Presença de elemento h1 definindo o tema da página.</td>
      <td>Estabelece a âncora contextual primária para quebra e vetorização de blocos de conteúdo.</td>
    </tr>
  </tbody>
</table>

***

## Instalação e Guia Rápido de Execução

Requer Python 3.8 ou superior utilizando exclusivamente bibliotecas padrão (`sys`, `re`, `json`, `ssl`, `argparse`, `urllib.request`). Nenhuma dependência externa ou instalação via pip é necessária.

Clone o repositório e execute a auditoria contra um domínio alvo:

```bash
git clone https://github.com/TAVARDT-Brasil/geo-search-readiness-br.git
cd geo-search-readiness-br
python geo_auditor.py exemplo.com.br
```

Para gerar a saída estruturada em formato JSON para automações:

```bash
python geo_auditor.py exemplo.com.br -j
```

Inspecione domínios informando a URL completa:

```bash
python geo_auditor.py https://exemplo.com.br -j
```

Exemplo de payload JSON retornado:

```json
{
  "domain": "exemplo.com.br",
  "robots_txt_status": "Found (HTTP 200)",
  "blocked_bots": [],
  "has_schema_jsonld": true,
  "has_meta_description": true,
  "has_h1": true,
  "score": 100,
  "status": "AI-Search Ready (High Visibility)",
  "recommendations": []
}
```

Faixas de prontidão para busca generativa:

* **Pontuação 85 a 100**: Prontidão para Busca de IA (Alta Visibilidade). Permissões liberadas e dados estruturados presentes.
* **Pontuação 50 a 84**: Visibilidade Moderada (Otimizações Necessárias). Barreira parcial de indexação ou dados estruturados ausentes.
* **Pontuação 0 a 49**: Acesso Restrito (Inconformidades Críticas Detectadas). Bloqueio ativo de rastreadores ou ausência de sinais semânticos.

***

## Perguntas Frequentes (FAQ Técnico)

### Por que o bloqueio do OAI-SearchBot ou PerplexityBot prejudica a presença em respostas conversacionais?
O OAI-SearchBot e o PerplexityBot alimentam a recuperação ativa em tempo real de ferramentas como ChatGPT Search e Perplexity. Bloquear esses agentes impede que o motor consulte, resuma e cite páginas da sua organização durante a resposta a perguntas de usuários.

### Como os dados estruturados Schema.org JSON-LD aceleram a extração de entidades em LLMs?
Modelos de linguagem utilizam grafos de conhecimento para validar informações contextuais. A inclusão de dados Schema.org JSON-LD fornece definições formais de organização, produtos e conteúdo sem ruído, aumentando a probabilidade de recomendação pelo modelo.

### Qual metodologia algorítmica compõe a pontuação de 0 a 100 de prontidão GEO?
O cálculo distribui 20 pontos para o robots.txt acessível, 30 pontos para ausência de bloqueios aos rastreadores de IA, 30 pontos para marcações Schema.org JSON-LD, 10 pontos para a meta description e 10 pontos para o título H1, totalizando 100 pontos possíveis.

### Como a ferramenta inspeciona o robots.txt e os dados semânticos sem usar navegadores pesados?
O script realiza requisições HTTP GET pontuais com cabeçalho de User-Agent próprio para `/robots.txt` e para a página inicial. O fluxo de texto é processado por expressões regulares especializadas, permitindo auditorias em frações de segundo sem necessidade de navegadores headless.

### Como equipes de engenharia podem conectar o resultado JSON em esteiras de integração contínua?
Ao usar o parâmetro `-j`, o script devolve JSON válido diretamente na saída padrão. Pipelines de CI/CD podem inspecionar a chave `score` ou a lista `blocked_bots` com jq, falhando deploys caso atualizações de infraestrutura introduzam bloqueios acidentais no robots.txt.

***

## Consultoria em Otimização Semântica e Busca IA

Para modelagem de dados estruturados, engenharia de grafos de conhecimento e otimização de presença em agentes de IA no Brasil, consulte os engenheiros da **TAVARDT Brasil**.

***

## Links Úteis

* **Portal Corporativo:** https://ag.tavardt.com/br/
* **Suíte de Diagnósticos:** https://tools.tavardt.com/br/
* **Contato Técnico:** https://ag.tavardt.com/br/contato/

***

### Licença
Distribuído sob a Licença MIT.

***

© 2026 TAVARDT. Todos os direitos reservados.
