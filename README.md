# Xbox Game Pass --- Dashboard de Assinaturas

## Visão geral

Este projeto apresenta um dashboard desenvolvido no Microsoft Excel para
analisar uma base de assinaturas fictícia do Xbox Game Pass ao longo de
2024. O objetivo é transformar registros de assinantes em indicadores de
faturamento e adesão a serviços adicionais, apoiando a leitura do
desempenho comercial.

O arquivo de trabalho contém quatro abas: - **Assets** --- paleta de
cores e referências visuais utilizadas no dashboard. - **Bases** ---
tabela com os registros de assinaturas. - **Cálculos** ---
tabelas-resumo e respostas às perguntas de negócio. - **Dashboard** ---
painel visual com período de análise e indicadores.

> **Observação:** os dados parecem ser demonstrativos/sintéticos. Os
> valores e resultados descritos neste README referem-se ao arquivo
> fornecido e não devem ser interpretados como números oficiais da
> Microsoft ou do Xbox.

## Perguntas de negócio

A aba **Cálculos** organiza análises para responder a estas perguntas:

1.  Qual é o valor total registrado para as assinaturas?
2.  Como o valor total se divide entre assinaturas com e sem renovação
    automática?
3.  Qual é o total registrado para o adicional EA Play Season Pass?
4.  Qual é o total registrado para o Minecraft Season Pass?

O arquivo também contém campos que permitem aprofundar a análise por
plano, periodicidade e data de início.

## Dados utilizados

A aba **Bases** possui 295 registros e 13 colunas. O período indicado no
painel é de **01/01/2024 a 31/12/2024**; na base observada, as datas de
início vão de **01/01/2024 a 16/12/2024**.

  -----------------------------------------------------------------------
  Campo                               Descrição
  ----------------------------------- -----------------------------------
  `Subscriber ID`                     Identificador do assinante

  `Name`                              Nome associado ao registro

  `Plan`                              Plano contratado: Core, Standard ou
                                      Ultimate

  `Start Date`                        Data de início da assinatura

  `Auto Renewal`                      Indica se a renovação automática
                                      está ativa (Yes/No)

  `Subscription Price`                Valor registrado para a assinatura
                                      principal

  `Subscription Type`                 Periodicidade: Monthly, Quarterly
                                      ou Annual

  `EA Play Season Pass`               Indica a presença do adicional EA
                                      Play

  `EA Play Season Pass Price`         Valor registrado para o adicional
                                      EA Play

  `Minecraft Season Pass`             Indica a presença do adicional
                                      Minecraft

  `Minecraft Season Pass Price`       Valor registrado para o adicional
                                      Minecraft

  `Coupon Value`                      Valor de cupom/desconto registrado

  `Total Value`                       Valor total calculado/registrado
                                      por assinatura
  -----------------------------------------------------------------------

### Resumo descritivo da base

-   **295** registros de assinantes.
-   **Planos:** Core (101), Ultimate (98) e Standard (96).
-   **Periodicidade:** Monthly (139), Quarterly (85) e Annual (71).
-   **Renovação automática:** Yes (148) e No (147).
-   **Soma de `Total Value`: 7.633** unidades monetárias, conforme os
    valores da planilha.
-   Na tabela-resumo existente, `Total Value` soma **3.786** para
    renovação automática ativa e **3.847** para renovação automática
    inativa.
-   O adicional EA Play apresenta total de **2.940** na tabela de
    cálculos.
-   O adicional Minecraft apresenta total de **3.880** na tabela de
    cálculos.

Os valores não têm moeda explicitamente documentada no arquivo; por
isso, este README não os identifica como reais, dólares ou outra moeda.

## Como interpretar os resultados

-   Compare o total por `Auto Renewal` para observar a distribuição do
    valor entre assinaturas com e sem renovação automática.
-   Analise `Plan` e `Subscription Type` para compreender a composição
    da carteira por categoria e periodicidade.
-   Examine os campos dos adicionais para avaliar a contribuição
    registrada do EA Play e do Minecraft.
-   Use `Start Date` para investigar a evolução dos registros ao longo
    do período.

**Atenção à interpretação:** os títulos das perguntas na aba `Cálculos`
mencionam planos anuais, mas algumas tabelas-resumo visíveis parecem não
aplicar um filtro explícito de `Subscription Type = Annual`. Antes de
apresentar os resultados como faturamento exclusivamente anual, confirme
os filtros das tabelas dinâmicas e a fórmula de `Total Value`.

## Ferramentas e recursos

-   **Microsoft Excel** --- armazenamento, fórmulas, tabelas e
    tabelas-resumo.
-   **Tabela estruturada `Tabela1`** na aba `Bases`.
-   **Elementos visuais e paleta de cores** documentados na aba
    `Assets`.
-   Abas separadas para dados de origem, cálculos e apresentação,
    facilitando a manutenção do arquivo.

O arquivo não contém gráficos nativos do Excel identificados na aba
`Dashboard`; o painel pode utilizar formas, caixas de texto, imagens ou
outros elementos visuais. Assim, não se presume que os indicadores sejam
atualizados automaticamente sem verificar as fórmulas, tabelas dinâmicas
e conexões existentes.

## Instruções para reproduzir

### Requisitos

-   Microsoft Excel (preferencialmente uma versão recente para preservar
    tabelas dinâmicas, segmentações e formatação).
-   O arquivo original `base_dasboard_xbox.xlsx`.

### Passo a passo

1.  **Baixe ou clone o projeto** e mantenha o arquivo Excel na pasta do
    projeto.
2.  **Abra `base_dasboard_xbox.xlsx` no Excel**. Se aparecer uma
    mensagem de segurança, habilite apenas o conteúdo em que confiar.
3.  Acesse a aba **Bases** e confira os cabeçalhos, os tipos de dados e
    o intervalo da tabela `Tabela1`.
4.  Para acrescentar dados, insira os novos registros dentro da tabela
    estruturada ou redimensione-a para incluir as novas linhas. Preserve
    os nomes e a ordem dos campos utilizados nos cálculos.
5.  Confira as fórmulas da coluna `Total Value` e os critérios aplicados
    aos campos de adicionais e cupons. A regra de cálculo deve ser
    validada antes de atualizar os indicadores.
6.  Na aba **Cálculos**, atualize as tabelas dinâmicas por **Dados →
    Atualizar Tudo** (ou clique com o botão direito em cada tabela
    dinâmica e escolha **Atualizar**).
7.  Verifique se os filtros correspondem à pergunta de negócio. Para
    analisar somente assinaturas anuais, aplique
    `Subscription Type = Annual` e confirme se todas as tabelas-resumo
    relevantes usam esse filtro.
8.  Acesse a aba **Dashboard** e valide se os números exibidos
    correspondem aos cálculos atualizados. Caso algum elemento seja
    estático, atualize-o manualmente ou conecte-o às células de cálculo.
9.  Salve uma cópia atualizada do arquivo para preservar a versão
    original.

### Reproduzir a partir do zero

1.  Importe os dados para uma planilha e converta o intervalo em
    **Tabela** (`Ctrl + T`).
2.  Dê à tabela um nome consistente, como `Tabela1`.
3.  Crie tabelas dinâmicas para somar `Total Value` por `Auto Renewal`,
    somar os valores dos adicionais por `Plan` e analisar a base por
    periodicidade.
4.  Crie o painel na aba `Dashboard`, vinculando cartões e gráficos às
    tabelas de cálculo.
5.  Aplique a paleta registrada na aba `Assets` e documente período,
    data de atualização, definições dos indicadores e moeda.

## Validações recomendadas

Antes de usar o dashboard em um relatório ou portfólio, recomenda-se:

-   Confirmar a unidade monetária e se os preços representam valor
    mensal, trimestral, anual ou valor total do contrato.
-   Validar a fórmula de `Total Value`, especialmente a forma como
    cupons/descontos são aplicados.
-   Conferir se os adicionais são somados como receita ou se seus campos
    indicam apenas adesão.
-   Corrigir/confirmar os filtros das perguntas sobre faturamento anual.
-   Registrar a data real de atualização dos dados; o painel informa
    `25/12/2024 09:00:00`.
-   Evitar divulgar nomes de pessoas caso os registros não sejam
    inteiramente fictícios; para publicação, prefira dados anonimizados.

## Estrutura sugerida do repositório

``` text
xbox-game-pass-dashboard/
├── README.md
└── base_dasboard_xbox.xlsx
```

## Limitações

Este projeto é uma análise em planilha, não uma aplicação web. A
reprodução depende do Excel e dos recursos existentes no arquivo. Os
resultados são descritivos e dependem da qualidade dos dados, das
fórmulas e dos filtros configurados. Este README documenta a estrutura
identificada no arquivo fornecido e destaca verificações necessárias;
não presume regras comerciais que não estejam explicitadas na planilha.

------------------------------------------------------------------------

**Projeto:** Xbox Game Pass --- Dashboard de Assinaturas\
**Período declarado no painel:** 01/01/2024--31/12/2024\
**Arquivo de origem:** `base_dasboard_xbox.xlsx`
# dasboard_xbox

[base_dasboard_xbox.xlsx](https://github.com/user-attachments/files/33401675/base_dasboard_xbox.xlsx)
