# Auditor de Busca com IA e GEO | TAVARDT Brasil

[![Auditor GEO](https://img.shields.io/badge/TAVARDT-Busca%20IA%20GEO-5b3cf5.svg)](https://tools.tavardt.com/br/auditor-busca-ia-geo/)
[![Jurisdicao](https://img.shields.io/badge/Jurisdicao-Brasil-00C853.svg)](https://ag.tavardt.com/br/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)

Auditor CLI de Generative Engine Optimization (GEO) para inspecao de permissões de crawlers de IA, dados estruturados Schema.org e prontidao semantica.

Desenvolvido e mantido pela divisao de engenharia semantica e busca da **[TAVARDT Brasil](https://ag.tavardt.com/br/)**.

---

## Capacidades de Auditoria GEO

* **Acesso de Rastreadores de IA**: Inspecao de diretivas de bloqueio em `robots.txt` para bots como GPTBot, OAI-SearchBot, PerplexityBot, ClaudeBot e Google-Extended.
* **Extracao de Entidades Semanticas**: Verificacao da presenca de marcacao estruturada Schema.org em formato JSON-LD.
* **Sinais Semanticos Fundamentais**: Checagem de hierarquia de titulos H1 e completude de meta descriptions para ancoragem contextual.
* **Pontuacao de Prontidao**: Diagnostico automatizado em escala de 0 a 100 pontos com recomendacoes tecnicas priorizadas.

---

## Instalacao e Execucao

Requer Python 3.8 ou superior sem dependencias externas.

```bash
git clone https://github.com/TAVARDT-Brasil/geo-search-readiness-br.git
cd geo-search-readiness-br
python geo_auditor.py empresa.com.br
```

Para gerar saida estruturada em JSON:

```bash
python geo_auditor.py empresa.com.br --json
```

---

## Diagnostico Completo na Web

Para auditorias continuas e analise comparativa de presenca em motores generativos, acesse a ferramenta oficial:

* **[Auditor de Busca com IA e GEO](https://tools.tavardt.com/br/auditor-busca-ia-geo/)**
* **[Portal Corporativo TAVARDT Brasil](https://ag.tavardt.com/br/)**

---

## Consultoria em Visibilidade e Motores de IA

Para otimizacao de arquitetura de dados e indexacao em agentes autonomos no Brasil, consulte os especialistas da **[TAVARDT Brasil](https://ag.tavardt.com/br/contato/)**.
