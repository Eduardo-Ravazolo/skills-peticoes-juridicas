# Fontes oficiais de jurisprudência (testadas em 10/2026)

Com navegador automatizado: `navigate` + leitura do texto da página. Se aparecer tela de "verificação automática" (STJ), aguardar 3–5 s e ler de novo. **CAPTCHA: pedir ao usuário que resolva; nunca resolver.**

## Tribunais superiores e nacionais
- **STF** — busca livre: `https://jurisprudencia.stf.jus.br/pages/search?base=acordaos&queryString=TERMOS&sort=_score&sortBy=desc` (base: `acordaos`, `repercussao-geral`, `sumulas`, `decisoes`). Traz classe/número, órgão, relator, datas, ementa, Tema e Tese.
  Tema de RG pelo número: `https://portal.stf.jus.br/jurisprudenciaRepercussao/tema.asp?num=NNN`.
- **STJ** — tema repetitivo: `https://processo.stj.jus.br/repetitivos/temas_repetitivos/pesquisa.jsp?novaConsulta=true&tipo_pesquisa=T&cod_tema_inicial=NNNN&cod_tema_final=NNNN` (situação, tese, REsps, relator, julgamento, publicação, embargos, trânsito).
  Súmulas: `https://scon.stj.jus.br/SCON/pesquisar.jsp?b=SUMU&livre=TERMOS` (indica CANCELADA). Acórdãos: `b=ACOR`; monocráticas: `b=DTXT`. A busca livre é ampla — filtrar por ramo e ler o enunciado.
- **TNU (JEF)** — temas representativos: `https://www.cjf.jus.br/cjf/corregedoria-da-justica-federal/turma-nacional-de-uniformizacao/temas-representativos` (campos: número, tese, situação). Súmulas no menu da mesma área.
- **TST** — `https://jurisprudencia.tst.jus.br/` (campos "e", "ou", "sem"; aspas; súmulas, OJs e PNs; botão "Ementa para citação").
- **CNJ — Banco Nacional de Precedentes** (`pangeabnp.pdpj.jus.br`) — pode exigir login.

## Tribunais regionais (adapte à sua região — exemplos da 4ª Região/RS)
- **TRF4 / TRU4** — `https://jurisprudencia.trf4.jus.br/pesquisa/pesquisa.php` (formulário; atalhos para IRDR, IAC, Súmulas; número completo do processo visível).
- **TJRS** — `https://www.tjrs.jus.br/buscas/jurisprudencia/` (formulário).
- **TRT4** — `https://www.trt4.jus.br` → Jurisprudência.

Para outras regiões, localizar a página oficial de jurisprudência do TRF, TJ e TRT correspondentes e registrar aqui o endereço e a forma de busca.

## Agregadores privados
Servem no máximo para **localizar** um precedente. Muitos mascaram o número do processo na versão gratuita. A identificação completa (número, órgão, relator, datas, ementa) vem sempre do site oficial.
