# Pesquisa e Escrita Científica com uso de IA

Esse texto contém a descrição de diversos recursos para usar a inteligência artificial na pesquisa e escrita científica. Contém desde o uso de assistentes e agentes de IA, até avançados recursos de programação em Python.

***Aviso importante:** as orientações a seguir têm o objetivo de apoiar estudantes e pesquisadores na elaboração de suas publicações científicas. Não dispensam, todavia, a leitura cuidadosa das regras de publicação de cada revista e de cada instituição, algumas possuem restrições severas para o uso da IA. Além disso, esse texto rejeita fortemente qualquer iniciativa que estimule plágio ou violação de direitos autorais.*

## Zotero

Existem ferramentas interessantes para catalogar publicações científicas de forma estruturada, em pastas, com extração dos metadados e padrões bibliográficos. Usar uma ferramenta desse tipo é um passo fundamental para ter um trabalho eficiente na pesquisa e escrita científica, mesmo que não seja feita por IA.

Em minha opinião, a melhor ferramenta desse tipo é a [Zotero](https://www.zotero.org/).

Ela possui um plugin para Chrome que salva a página com o artigo que você está visitando na pasta ("collection") que você determinar, extraindo automaticamente os seus metadados. Além disso, a Zotero possui uma [API](https://www.zotero.org/support/dev/web_api/v3/start) e várias outras [ferramentas](https://www.zotero.org/support/dev/start) para desenvolvedores, as quais serão usadas nesse documento.

Nesse [arquivo](zotero/connect_zotero.ipynb) você encontrará um exemplo de como usar a API da Zotero.

O mais importante: Zotero é totalmente gratuita, não é fremium.

Existem outras ferramentas desse tipo, tal como [Mendeley](https://www.mendeley.com/), mas eu nunca usei, pois estou muito satisfeito com a Zotero. Além disso, a Zotero por ser open source, é a ferramenta de eleição para a integração com alguns agentes de IA que serão citados a seguir.

---

# Buscar

## Sem IA

A busca de publicações científicas pode ser feita de forma determinística, ou seja, em recursos tradicionais, tais como:

- [Google Scholar](https://scholar.google.com.br)
- [Semantic Scholar](https://www.semanticscholar.org)
- [PubMed](https://pubmed.ncbi.nlm.nih.gov)
- [ArXiv](https://arxiv.org)

Uma forma interessante de explorar essas fontes é realizar a busca, analisar a lista de publicações e, ao clicar na publicação desejada, clicar no plugin da Zotero. Isso salva automaticamente o link e os dados da publicação, você não precisa criar bookmarks e nem copiar/colar a URL encontrada, já vai tudo para a pasta que você determinou.

## Assistentes de IA

Os assistentes de IA (ChatGPT, Gemini, etc.) permitem realizar buscas de publicações, porém deve-se ter muito cuidado, pois não é raro haver alucinações, as quais podem ser de três tipos:

- Alucinação tipo 1: a URL da publicação não existe, dá uma página nula.
- Alucinação tipo 2: a URL existe, mas remete a outra publicação.
- Alucinação tipo 3: a URL existe, aponta para a publicação correta, mas o texto não sustenta a menção.

O recurso "Deep Research", presente na maioria dos assistentes, reduz essas alucinações, mas ainda assim não as elimina. Alguns assistentes, como o [Perplexity](https://www.perplexity.ai/), estão mais estruturados para fornecer resultados mais consistentes.

## MCPs

Uma forma segura de fazer esse tipo de busca com assistentes de IA é o uso de MCPs específicos. Os MCPs funcionam como uma espécie de plugin, que adicionam mais capacidades aos assistentes. Atualmente, apenas o [Claude](https://claude.ai) tem recurso nativo para adicionar MCPs. Outros não têm esse recurso, ou têm de forma limitada.

O Claude tem nativamente MCPs para **PubMed** e **Scholar Gateway**.

Além deles, é possível instalar outros como:

- [Paper Search](https://github.com/openags/paper-search-mcp)
- [ArXiv](https://github.com/jasonleinart/arxiv-mcp-server)
- [CrossRef](https://mcpservers.org/servers/JackKuo666/Crossref-MCP-Server)
- [Semantic Scholar](https://mcpservers.org/servers/FujishigeTemma/semantic-scholar-mcp)

## Agentes de IA

Muitos agentes de IA tem surgido, com a promessa de realizar buscas mais seguras de publicações científicas, tais como:

- [AnswerThis](https://answerthis.io)
- [Borium](https://www.bohrium.com)
- [Elicit](https://elicit.com)
- [Scispace](https://scispace.com) - esse tem integração com a Zotero.
- [Scite](https://scite.ai)

Alguns performam muito bem, mas todos são pagos, com planos gratuitos de acesso limitado.

## Com Python

Há várias APIs que permitem fazer buscas de publicações científicas. Os arquivos a seguir trazem exemplos de algumas delas:

- [Semantic Scholar](search/search_semantic_scholar.ipynb)
  Tradicional base de dados com milhares de publicações em todas as áreas. Não é preciso de chave da API, mas é possível obter uma, a qual permite consultas mais frequentes.
- [Serpapi](search/search_serpapi.ipynb)
  Permite acesso programático ao Google Scholar. O pacote gratuito permite 2500 consultas por mês.
- [Newspaper](search/search_newspaper.ipynb)
  Uma API com vários recursos. No exemplo do arquivo, ela permite mapear um determinado site e extrair notícias no formato de um news feed.
- [Web search](search/search_websearch.ipynb)
  Esse arquivo faz programaticamente uma pesquisa na web com um assistente de IA (no caso, o da OpenAI). Notar a parte de `tools`.
- [MCP search](search/search_mcpsearch.ipynb)
  Esse arquivo faz programaticamente uma pesquisa na web com um assistente de IA (no caso, o da OpenAI), usando uma MCP. Notar a parte de `tools`.

---

# Ler

## Assistentes de IA

Os assistentes de IA (ChatGPT, Gemini, etc.) podem ajudar na leitura de publicações científicas. Todos eles possuem o recurso de anexar arquivos e acessar a web, portanto basta anexar o arquivo da publicação ou passar o respectivo link e pedir para resumir, tirar dúvidas, destacar pontos, etc.

## Notebooks

Todavia, há algumas ferramentas com mais recursos, que permitem ações mais avançadas. Os chamados "notebooks" (cadernos) são os mais indicados. Além de oferecer a possibilidade de resumir e tirar dúvidas, eles criam mapas mentais, linhas do tempo, elaboram podcasts e alguns até vídeos. Exemplos:

- [Google NotebookLM](https://notebooklm.google.com)
- [Microsoft Notebooks](https://m365.cloud.microsoft/notebooks)
- [Coral AI](https://app.getcoralai.com)

A OpenAI lançou também um notebook, porém até o momento existe apenas a versão para baixar e instalar localmente, o que demanda conhecimentos um pouco mais avançados, incluindo Docker. Clique [aqui](https://www.open-notebook.ai) para saber mais.

## Agentes de IA

Existem alguns agentes de IA interessantes para ajudar na leitura e compreensão de publicações científicas.

- [Litmaps](https://www.litmaps.com)
  Esse agente, além de fazer a busca de artigos, acha também artigos relacionados, criando grafos de relacionamento. Além disso, na versão Pro, possui integração com a Zotero, permitindo manter os mapas sincronizados com as coleções da Zotero.
- [Consensus](https://consensus.app)
  Ao se fazer uma determinada pergunta a esse agente, ele pesquisa uma série de fontes e cria uma análise de consenso (como diz o nome). Para tanto, aponta artigos que suportam positivamente a pergunta feita, bem como negativamente, construindo mapas visuais.

## Com Python

O uso de APIs permitem resgatar artigos específicos, criando possíveis automações, conforme os exemplos a seguir:

- [Newspaper](read/read_newspaper.ipynb)
  Esse script mostra como usar a API do Newspaper para baixar um artigo específico, a partir de sua URL, extraindo suas partes, inclusive o resumo (abstract). Não necessita de chave de API.
- [Crossref](read/read_crossref.ipynb)
  A API do Crossref (não necessita de chave) também permite baixar um artigo específico, porém a partir de seu DOI (Digital Object Identifier). É uma API mais detalhada que a do Newspaper, extraindo informações mais detalhadas do artigo, diretamente da base de dados da própria Crossref.

Esses scripts mostram apenas o acesso a um artigo, mas se forem combinados com os scripts de buscas mencionados anteriormente, podem criar interessantes fluxos de automação. Por exemplo, um script de busca encontra uma lista de artigos, um segundo script extrai o resumo de cada um e um terceiro, usando um LLM, faz uma resumo completo. Isso pode ser automatizado e, por exemplo, rodar semanalmente, permitindo ao pesquisador receber um relatório atualizado de tudo que está saindo em sua área.

O mesmo pode ser feito com a API da Zotero. Por exemplo, o pesquisador navega em diversos artigos e faz a sua seleção própria em uma coleção da Zotero. Depois, um script acessa essa coleção, recupera o DOI de cada uma e usando a Crossref faz a leitura e um resumo completo. Se o resumo estiver disponível na própria Zotero, nem será necessário acessar a Crossref. Veja nessa [script](zotero/summarize_zotero.ipynb) um exemplo de como fazer isso.

---

# Escrever

## Assistentes de IA

Os assistentes de IA são poderosos elaboradores de texto, essa é talvez uma de suas melhores funcionalidades. Usuários experientes podem conseguir resultados fabulosos com esses assistentes, preservando a originalidade e o estilo pessoal de sua redação.

Por exemplo, é possível colocar vários resumos em sequência (extraídos com os recursos anteriores) e pedir para criar um texto coerente. Se forem anexados textos anteriores escritos pelo pesquisador, é possível pedir para presevar o seu estilo pessoal. Essa é uma sugestão de prompt que pode ser usado para orientar uma IA na redação de um artigo científico com base em resumos fornecidos e textos anteriores do autor.

```text
  Você é um assistente especializado em redação científica avançada. 
  
  Sua tarefa é elaborar um artigo científico completo, com extensão total de 2 laudas (aproximadamente 1.200 a 1.500 palavras), a partir de uma série de resumos que serão apresentados a seguir.  

  Siga estas instruções com atenção:

  1. Utilize os resumos como base factual e conceitual para construir o artigo. Faça conexões lógicas entre eles e desenvolva uma narrativa científica coerente.

  2. Mantenha o estilo, o tom e a estrutura argumentativa do autor original. Para isso, analise os textos anexados como exemplos — observe seu vocabulário, ritmo, nível de formalidade, tipos de transição de ideias e padrões de citação.

  3. Estruture o artigo no formato acadêmico tradicional:
    - Título conciso e técnico
    - Resumo (abstract)
    - Introdução clara com contextualização e objetivo
    - Desenvolvimento organizado em subtópicos
    - Considerações finais que sintetizem os resultados e eventuais perspectivas futuras
    - Referências (modelo ABNT)

  4. Evite redundâncias e ambiguidade. Priorize clareza, coerência e consistência conceitual.

  5. Preserve o vocabulário técnico da área e empregue conectivos adequados à argumentação científica.

  6. O texto final deve soar natural e autêntico, como se fosse escrito integralmente pelo autor referenciado.

  Instruções adicionais:
  - Caso os resumos apresentem lacunas, realize inferências plausíveis e devidamente contextualizadas.
  - Não inclua trechos literais dos exemplos anexados, apenas adote seu estilo.
  - Certifique-se de que o artigo atenda rigor científico e coesão textual dentro do limite de 2 laudas.

  Agora, aguarde a inserção dos resumos e dos textos de referência antes de redigir o artigo final.
```

Alguns assistentes, como ChatGPT, Gemini e Perplexity, possuem o recurso "Canvas" ou "Pages". Ao se ativar esse recurso, o texto produzido será exibido em uma parte lateral, que funciona como um editor de texto, você poderá alterar, cortar e fazer ajustes. Além disso, conforme o assistente utilizado, é possível selecionar uma determinada parte do texto e pedir ações como ampliar, reduzir, corrigir, traduzir, transformar em tabela, criar bullets, entre outras. Isso vale, obviamente, para qualquer idioma.

Pessoalmente, quando uso recursos desse tipo, eu prefiro ir construindo o texto aos poucos. Ou seja, en vez de usar um prompt como o citado acima, eu abro um canvas vazio, crio as seções que me interessam manualmente e vou pedindo ajuda para a IA em cada etapa. Isso me dá mais controle do texto final. Mas é uma questão de estilo pessoal.

## Editores de texto

Os principais editores de texto atuais possuem integração com assistentes de IA. O Microsoft Word está integrado com o Copilot e o Google Docs, com o Gemini. Essas integrações permitem que os editores funcioname como os "Canvas/Pages" citados anteriormente. Ou seja, é possível pedir para IA escrever o texto, bem como fazer ajustes e correções.

## Agentes de IA

Da mesma que forma que foi citado nas outras seções, diversas soluções comerciais têm surgido como agentes de IA para a redação de publicações científicas, tanto artigos para revistas, até mesmo dissertações e teses completas.

Eis alguns exemplos:

- [Gatsbi](https://www.gatsbi.com)
- [Grammarly](https://www.grammarly.com)
- [Jenni AI](https://jenni.ai)
- [Paperpal](https://paperpal.com)
- [Quilbot](https://quillbot.com)
- [Thesify](https://www.thesify.ai)
- [Thesis AI](https://www.thesisai.io)

Alguns agentes de IA estão especializados na detecção, tanto de plágio, quanto de uso da IA. Exemplos:

- [Pangram](https://www.pangram.com)
- [Turnitin](https://www.turnitin.com.br)
- [Originality](https://originality.ai)
- [GPTZero](https://gptzero.me)

Já outros agentes são especializados em deixar os textos mais "humanizados", supostamente sem a impressão de terem sido gerados por IA. Exemplos:

- [Undetectable](https://undetectable.ai)
- [Phrasly](https://phrasly.ai)
- [Humanize](http://humanizeai.pro)

## Com Python

Scripts de Python podem criar fluxos automatizados completos para a redação de textos, a partir de publicações previamente selecionadas.

Esse [script](zotero/write_zotero.ipynb) mostra uma exemplo de como elaborar um texto completo usando uma coleção da Zotero.

---

# Para seguir

Profa. Fernanda
[https://www.instagram.com/pesquisanapratica](https://www.instagram.com/pesquisanapratica)

Andy Stapleton
[https://www.youtube.com/@DrAndyStapleton](https://www.youtube.com/@DrAndyStapleton)

.
