# Evidências de testes — Energia que dá Lucro

Os dados de loja e consumo são fictícios. As evidências estão em `../evidencias/prints/` e as cópias dos arquivos de controle em `../evidencias/registros/`. Os controles em `../dados/exemplos/` são inicializados vazios para novas demonstrações.

| Caso | Procedimento observado | Resultado | Evidência |
|---|---|---|---|
| Envio de alertas | Executar o fluxo com eventos elegíveis. | Fluxo concluído e dois alertas recebidos, de 95 e 120 segundos. | 01 e 02 |
| Regras e auditoria | Consultar os registros de alertas. | Quatro envios acumulados; auditados casos ignorados, inválidos e duplicados. | 03 e 04 |
| Envio de resumos | Executar a demonstração com duas lojas e dois períodos. | Quatro itens chegaram ao nó de envio, quatro mensagens aparecem no Gmail e quatro constam no controle. | 05, 06, 07 e 08 |
| Repetição dos resumos | Executar novamente com os mesmos períodos e controle. | Os quatro itens seguiram pelo caminho de não envio; não chegou e-mail novo e os logs indicam duplicidade. | 10 e 11 |
| Falha manual | Execução manual com problema na leitura/interpretação dos eventos. | Erro no nó `Interpretar eventos`, exibido como `{}` no editor. A imagem não confirma o processamento pelo workflow de erro. | 09 |

As imagens mostram o resultado no momento da captura. A confirmação de SMTP no controle indica aceitação pelo servidor; a caixa de entrada demonstra o recebimento daquelas mensagens de teste. Os testes não comprovam execução automática por agendamento, tratamento automático de erro, tolerância a concorrência ou funcionamento para todos os dados possíveis.

Para uma nova demonstração, siga a preparação do README, use cópias dos controles vazios, configure destinos próprios, execute um fluxo por vez e preserve os resultados em arquivos separados. A repetição deve usar os mesmos controles para exercitar a prevenção de duplicidade.
