# LEIAME.md

Este arquivo contém o detalhamento de todas as funções utilizadas no Jupyter Notebook B3_analiseDadosV4m.ipynb, incluindo descrição, entradas e saídas.

## 1. analisa_registro(reg)
**Descrição:** Analisa o registro histórico da B3, retorna dicionário 'registro' com os campos extraídos da string do registro.

**Entradas:**
- reg (str): String do registro a ser analisado.

**Saídas:**
- registro (dict): Dicionário contendo os campos extraídos do registro (DATAPREG, CODBDI, CODNEG, etc.).

## 2. printTimesTerminal(arq, readT, create_dfT, saveT, filterT, totalT, totalRegs)
**Descrição:** Imprime no terminal os tempos de execução de várias operações.

**Entradas:**
- arq (str): Nome do arquivo.
- readT (float): Tempo de leitura.
- create_dfT (float): Tempo de criação do DataFrame.
- saveT (float): Tempo de salvamento.
- filterT (float): Tempo de filtragem.
- totalT (float): Tempo total.
- totalRegs (int): Total de registros.

**Saídas:** None (apenas imprime no terminal).

## 3. executionTimes(mensagem, read_time, df_time, save_time, filter_time, total_time)
**Descrição:** Registra os tempos de execução em um arquivo de log.

**Entradas:**
- mensagem (str): Mensagem a ser registrada.
- read_time (float): Tempo de leitura.
- df_time (float): Tempo de criação do DataFrame.
- save_time (float): Tempo de salvamento.
- filter_time (float): Tempo de filtragem.
- total_time (float): Tempo total.

**Saídas:** None (grava em arquivo b3_logs/execution_times.txt).

## 4. reg_erros(mensagem)
**Descrição:** Registra mensagens de erro em um arquivo de log.

**Entradas:**
- mensagem (str): Mensagem de erro.

**Saídas:** None (grava em arquivo b3_logs/erros.txt).

## 5. faz_o_IF(df_entrada, saida, destino, ano)
**Descrição:** Verifica o formato de saída e salva o DataFrame no destino correto (csv, pickle ou parquet).

**Entradas:**
- df_entrada (DataFrame): DataFrame a ser salvo.
- saida (str): Formato de saída ('csv', 'pickle', 'parquet').
- destino (str): Pasta de destino.
- ano (str): Ano dos dados.

**Saídas:** None ou 'ERRO' em caso de parâmetro inválido.

## 6. process_V2_b3_data_ZIP(arquivo)
**Descrição:** Processa arquivos ZIP para CSV, lendo arquivos da pasta b3_zip e salvando em b3_csv/b3_data.

**Entradas:**
- arquivo (str): Nome do arquivo sem extensão .ZIP.

**Saídas:**
- total_regs_ano (int): Total de registros processados no ano.

## 7. processa_arqs_zip(lista_zip)
**Descrição:** Processa todos os arquivos ZIP da lista para CSV.

**Entradas:**
- lista_zip (list): Lista de nomes de arquivos ZIP.

**Saídas:** None.

## 8. process_b3_data_csv(arquivo, saida)
**Descrição:** Converte e filtra arquivos CSV da B3 para formatos parquet, pickle ou csv, filtrando mercados avista, FIIs e fracionário.

**Entradas:**
- arquivo (str): Nome do arquivo CSV.
- saida (str): Formato de saída.

**Saídas:**
- total_regs_ano (int): Total de registros processados.

## 9. filtraMercAvistaFIIfrac(listaArqs, saidaForm)
**Descrição:** Filtra mercados avista, FIIs e fracionário usando a função process_b3_data_csv.

**Entradas:**
- listaArqs (list): Lista de arquivos a processar.
- saidaForm (str): Formato de saída.

**Saídas:** None.

## 10. process_b3_To_BDR_units_etc(arquivo, saida)
**Descrição:** Identifica e filtra códigos de BDR, UNITS, ações ON/PN e outros papéis, salvando em pastas separadas.

**Entradas:**
- arquivo (str): Nome do arquivo CSV.
- saida (str): Formato de saída.

**Saídas:**
- regsacaoONPNBR (int): Número de registros de ações ON/PN/BR.

## 11. filtra_BDRs_ONPN_etc(pasta_csv, saida_etc)
**Descrição:** Filtra ações ON/PN, BDRs, Units e outros papéis usando process_b3_To_BDR_units_etc.

**Entradas:**
- pasta_csv (str): Pasta com arquivos CSV.
- saida_etc (str): Formato de saída.

**Saídas:** None.

## 12. converte_formata_arq_ibov()
**Descrição:** Converte arquivos de evolução diária do IBOV de formato BR para formato USA.

**Entradas:** None.

**Saídas:** None.

## 13. lista_valores_unicos_por_ano(input_dir, column_name, output_file)
**Descrição:** Extrai valores únicos de uma coluna por ano e salva em um arquivo CSV.

**Entradas:**
- input_dir (str): Diretório de entrada.
- column_name (str): Nome da coluna.
- output_file (str): Arquivo de saída.

**Saídas:** None.

## 14. ListaValoresUnicosMercadoAvista()
**Descrição:** Lista valores únicos de CODNEG para mercado avista de 2000 a 2026.

**Entradas:** None.

**Saídas:** None.

## 15. verifica_Qtd_acoesUnicasAno()
**Descrição:** Verifica quantidade de ações únicas por ano e salva em CSV.

**Entradas:** None.

**Saídas:**
- lista_totAno (list): Lista com totais por ano.

## 16. graf_AcoesUnicas2000_2026()
**Descrição:** Cria gráfico da quantidade de ações únicas de 2000 a 2026 usando Plotly.

**Entradas:** None.

**Saídas:** None.

## 17. quaisComunsAtodosAnos()
**Descrição:** Identifica ações comuns a todos os anos desde 2000.

**Entradas:** None.

**Saídas:** None.

## 18. calculaTOTRegistros2000_2026_csv()
**Descrição:** Calcula total de registros usando pandas em arquivos CSV.

**Entradas:** None.

**Saídas:** None.

## 19. calculaTOTRegistros2000_2026_parquet()
**Descrição:** Calcula total de registros usando pandas em arquivos Parquet.

**Entradas:** None.

**Saídas:** None.

## 20. calculaTOTRegistros2000_2026_pyarrow()
**Descrição:** Calcula total de registros usando PyArrow em arquivos Parquet.

**Entradas:** None.

**Saídas:** None.

## 21. calculaVOLTOTporAnoPorMercado()
**Descrição:** Calcula soma de VOLTOT por ano e mercado, salvando em CSV.

**Entradas:** None.

**Saídas:** None.

## 22. calculaVOLTOT_AnoTodosMercados()
**Descrição:** Junta volumes de todos os mercados em um DataFrame e salva.

**Entradas:** None.

**Saídas:** None.

## 23. plotlyVolumeFinMercadosB3()
**Descrição:** Cria gráfico de volumes financeiros dos mercados da B3 usando Plotly.

**Entradas:** None.

**Saídas:** None.

## 24. corrigir_codneg_2025(filepath)
**Descrição:** Corrige códigos de ações (EMBR3 -> EMBJ3, ELET3 -> AXIA3) a partir de 2025-09-01.

**Entradas:**
- filepath (str): Caminho do arquivo CSV.

**Saídas:** None.

## 25. leListaRkAcao(ano_mes)
**Descrição:** Lê ranking de ações do IBOV e retorna DataFrame com código e porcentagem.

**Entradas:**
- ano_mes (str): Ano e mês (ex: '202602').

**Saídas:**
- df_rk (DataFrame): DataFrame com ranking.

## 26. leCotAcao(acao, inicio, fim, mercado)
**Descrição:** Lê cotações de uma ação de um mercado e salva em CSV.

**Entradas:**
- acao (str): Código da ação.
- inicio (str): Data de início.
- fim (str): Data de fim.
- mercado (str): Mercado (ex: 'mercado_acaoONPNBR').

**Saídas:** None.

## 27. LeTodasAcoesRankingAnoMes(rk_anoMes)
**Descrição:** Lê cotações de todas as ações do ranking para um ano/mês.

**Entradas:**
- rk_anoMes (str): Ano e mês do ranking.

**Saídas:** None.

## 28. concatenaTop20de2025e26()
**Descrição:** Concatena cotações das top 20 ações de 2025 e 2026.

**Entradas:** None.

**Saídas:** None.

## 29. carregaTop21Pesos()
**Descrição:** Carrega pesos das top 21 ações no IBOV.

**Entradas:** None.

**Saídas:**
- top21 (list): Lista de ações.
- pesos (dict): Dicionário de pesos.

## 30. carregaCotacoesTop2526()
**Descrição:** Carrega cotações das top 21 ações de 2025-2026.

**Entradas:** None.

**Saídas:**
- df_cotacoes (dict): Dicionário de séries de cotações.

## 31. load_ibov_data(year, month=None)
**Descrição:** Carrega dados diários de evolução do IBOV.

**Entradas:**
- year (int): Ano.
- month (int, optional): Mês.

**Saídas:**
- df_melted['IBOV'] (Series): Série do IBOV.

## 32. calc_retornos_diarios_top21_ibov()
**Descrição:** Calcula retornos diários das top 21 ações e do IBOV.

**Entradas:** None.

**Saídas:**
- retorno_ibov (Series): Retornos do IBOV.
- retorno_top21 (Series): Retornos das top 21.
- ibov (Series): Valores do IBOV.

## 33. calc_retornos_acumulados_top21_ibov()
**Descrição:** Calcula retornos acumulados das top 21 e IBOV.

**Entradas:** None.

**Saídas:**
- retorno_top21_acum (Series): Retornos acumulados top 21.
- retorno_ibov_acum (Series): Retornos acumulados IBOV.

## 34. contribuicao_TOP21_IBOV(ret_TOP21ac, ret_IBOVac)
**Descrição:** Cria gráficos de contribuição das top 21 no IBOV.

**Entradas:**
- ret_TOP21ac (Series): Retornos acumulados top 21.
- ret_IBOVac (Series): Retornos acumulados IBOV.

**Saídas:** None.

## 35. plotlyCorrelacao_TOP21_IBOV(retorno_top21, retorno_ibov)
**Descrição:** Cria gráfico de correlação entre retornos diários top 21 e IBOV.

**Entradas:**
- retorno_top21 (Series): Retornos top 21.
- retorno_ibov (Series): Retornos IBOV.

**Saídas:** None.

## 36. plotlyGraficoInfluenciaTop21_IBOV()
**Descrição:** Cria gráfico de influência das top 21 ações no IBOV.

**Entradas:** None.

**Saídas:** None.