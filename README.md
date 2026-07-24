# Análise da Biblioteca Steam via API

Projeto da disciplina de Extração e Análise de Dados, aplicando o conceito de consumo de
API real. A ideia foi analisar minha própria biblioteca de jogos na Steam, cruzando dados
de duas fontes diferentes.

## Fontes de dados

- **Steam Web API** — biblioteca de jogos, horas jogadas e data do último acesso
- **SteamSpy API** — gênero, preço e avaliações (positivas/negativas) de cada jogo

## O que o pipeline faz

1. **Extração** — consome a API oficial da Steam (biblioteca de jogos) e a API pública
   da SteamSpy (dados complementares de cada jogo).
2. **Limpeza** — remove duplicatas, corrige tipos de dado e padroniza texto, mantendo
   valores ausentes como "sem dado" (em vez de assumir 0 ou "gratuito" por engano).
3. **Integração** das duas fontes por ID do jogo.
4. **Transformação** — cria colunas novas como preço em dólar, percentual de avaliações
   positivas, dias desde o último login, faixa de preço, categoria de consumo (casual,
   engajado, hardcore) e custo por hora jogada.
5. **Análise exploratória** — concentração de horas jogadas, jogos nunca jogados,
   retenção ao longo de 3 anos, top jogos e perfil de consumo.
6. **Visualização** — gráficos de concentração de horas, atividade recente e distribuição
   por categoria de consumo.
7. **Insights finais** — gênero predominante, perfil de consumo, jogos "esquecidos",
   melhor custo-benefício e aprovação média da biblioteca.

## Tecnologias

Python, Pandas, Requests (para consumir as APIs) e Matplotlib.

## Como rodar

Este projeto usa uma chave de API pessoal da Steam (gratuita, gerada em
steamcommunity.com/dev/apikey) para acessar dados do próprio perfil — por isso, ele foi
feito para rodar localmente (Jupyter/VS Code), onde a chave é digitada de forma oculta
durante a execução e não fica salva em nenhum arquivo.
