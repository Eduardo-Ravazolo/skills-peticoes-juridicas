---
name: peticoes-juridicas
description: Use ao redigir, revisar ou formatar petições (iniciais, réplicas, recursos, requerimentos e recursos ao INSS/CRPS) e ao buscar jurisprudência consolidada nos sites oficiais dos tribunais para fundamentá-las.
---

# Petições + jurisprudência consolidada

Ciclo completo: **pesquisar** precedentes verídicos nos sites oficiais (Parte A), **redigir** com estrutura e redação persuasiva (Parte B), **gerar o .docx** no modelo do escritório (Parte C) e **revisar** antes de entregar (Parte D). Material de apoio:

- `references/fontes-oficiais.md` — onde e como buscar jurisprudência em cada tribunal.
- `scripts/gerar_peticao.py` e `scripts/checa_texto_oculto.py`.

*Versão gratuita.* A versão **Pro** acrescenta: roteiro judicial e administrativo de todos os benefícios do INSS com as Instruções Normativas vigentes, guia de escrita para as ferramentas de IA dos tribunais, skill de protocolos de julgamento do CNJ (gênero, racial, pessoa com deficiência) e atualizações periódicas.

**Configuração do escritório**: ler `config/escritorio.json` (nome, cidade, tribunais da região, modelo .docx, fonte, assinaturas). Se não existir, pedir ao usuário os dados e o arquivo de modelo antes de gerar a peça.

> Aviso: esta skill é ferramenta de apoio. Toda peça deve ser revisada e assinada por advogado(a) habilitado(a). Normas e precedentes mudam: confira sempre a fonte oficial na data de uso.

---

# PARTE A — JURISPRUDÊNCIA (somente fontes oficiais)

Nunca usar agregadores privados como fonte final. Nunca citar número, relator, data, ementa ou tese que não tenha sido lido nesta sessão no site oficial do tribunal.

## A1. Delimitar a tese
- Tese em 1 frase; definir a competência (Justiça Federal/JEF, Estadual, Trabalho) e os tribunais competentes, incluindo os regionais indicados no config.
- 2–4 combinações de termos curtos (2–3 palavras técnicas).

## A2. Ordem de força (art. 927 do CPC)
1. Súmula Vinculante / controle concentrado (STF) → 2. Repercussão Geral → 3. Repetitivos/IAC (STJ), IRR (TST) → 4. Súmulas STF/STJ, súmulas/OJs/PNs do TST → 5. IRDR/IAC/súmulas do TRF, TJ e TRT da região → 6. TNU/TRU → 7. Acórdãos reiterados e recentes do tribunal que julgará a causa.

## A3. Onde buscar
Ver `references/fontes-oficiais.md`. Portal fora do ar → avisar, tentar outro tribunal competente, marcar **[CONFIRMAR]**. Nunca completar dados de memória.

## A4. Checagens
Súmula vigente ou cancelada; tema julgado, afetado, sobrestado, revisado ou cancelado; embargos, modulação, superação; datas de julgamento, publicação e trânsito; aplicação recente.

## A5. Lado contrário
Buscar precedentes desfavoráveis à tese e relatar ao usuário com a distinção possível; não colocar na petição.

## A6. FORMATO OBRIGATÓRIO DA CITAÇÃO
1. **Ementa literal e completa** do site oficial, começando por "EMENTA:" (com I. CASO EM EXAME… IV. DISPOSITIVO E TESE, "Tese de julgamento", "___________", "Dispositivos relevantes citados", "Jurisprudência relevante citada", quando existirem). Sem resumir, parafrasear ou corrigir; cortes só com "(...)".
2. **Grifo em negrito** apenas no que sustenta a tese da petição.
3. **Referência** logo após: `(TRIBUNAL, CLASSE NÚMERO-COMPLETO, ÓRGÃO JULGADOR, Relator(a) NOME, julgado em DD/MM/AAAA)`; precedente qualificado acrescenta o tema (`– Tema 1.090/STJ`). Sem número completo, o julgado **não entra** na peça.
4. **"(grifei)"** ao final quando houver grifo.

Exemplo: "EMENTA: DIREITO PREVIDENCIÁRIO. EMBARGOS DE DECLARAÇÃO EM APELAÇÃO CÍVEL. AUXÍLIO-ACIDENTE. (...) 5. **A aplicação do Tema 416 do STJ pressupõe a comprovação da redução da capacidade laboral, ainda que em grau mínimo.** (...)" (TRF4, AC 5008278-16.2025.4.04.7101, 6ª Turma, Relatora ANDRÉIA MOMOLLI, julgado em 14/10/2026) (grifei)

- Súmula: enunciado literal + `(Súmula NNN do STJ, ÓRGÃO, julgado em ..., DJe ...)`.
- Tese de tema sem ementa: tese literal + `(STJ, Tema Repetitivo 1.090, REsp 2.082.072/RS, Primeira Seção, Relatora MARIA THEREZA DE ASSIS MOURA, julgado em 09/04/2025)`.
- Doutrina: autor, obra, edição, editora, ano e página; sem referência completa, marcar [CONFIRMAR REFERÊNCIA] ou retirar.
- Normas do INSS: "art. X da IN PRES/INSS nº 128/2022, com redação dada pela IN PRES/INSS nº Y/AAAA".

---

# PARTE B — ESTRUTURA E REDAÇÃO

## B1. Antes de escrever
- Ler todos os documentos do cliente e montar uma linha do tempo com datas e números (NB, DER, DIB, DCB, CID, CBO, processo).
- Nunca inventar fato, data, número de documento ou dado pessoal. O que faltar fica como `{{CAMPO}}` destacado e listado ao usuário no final.

## B2. Estrutura padrão — petição inicial
1. **Endereçamento** (negrito, caixa alta) ao juízo competente — Justiça Estadual para acidente do trabalho; Justiça Federal/JEF para os demais benefícios do INSS.
2. **Qualificação** (nome em negrito; nacionalidade, estado civil, profissão, RG, CPF, endereço, e-mail) + "vem, com o devido respeito, perante Vossa Excelência, por meio de seus procuradores signatários, propor a presente"
3. **Nome da ação** (negrito, centralizado, caixa alta) + "em face de **RÉU** … pelos fundamentos fáticos e jurídicos que passa a expor:"
4. Seções em algarismos romanos (Título 2): I. QUADRO-RESUMO (nos benefícios por incapacidade, o quadro da Lei 14.331/2022: processo administrativo, enfermidade/CID/especialidade, ocupação/CBO) · II. DA COMPETÊNCIA · III. DOS FATOS E DAS PROVAS · IV. DOS FUNDAMENTOS JURÍDICOS (subtópicos numerados, Título 3) · V. DA PROVA PERICIAL (quando houver) · VI. DA TUTELA PROVISÓRIA · VII. DA AUDIÊNCIA DE CONCILIAÇÃO · VIII. DOS PEDIDOS E REQUERIMENTOS · valor da causa · fecho · ROL DE QUESITOS (quando houver perícia).
5. Para benefícios do INSS, conferir requisitos, carência, qualidade de segurado e termo inicial na Lei 8.213/91, no Decreto 3.048/99 e na Instrução Normativa vigente do INSS antes de redigir.
6. Escrever de forma que a peça seja fácil de resumir: quadro-resumo no início, títulos descritivos, dados importantes escritos no texto (não só em imagem) e pedidos numerados e autossuficientes.

## B3. Outras peças
- **Réplica**: síntese da contestação → preliminares uma a uma → mérito ponto a ponto com prova dos autos → impugnar documentos → reiterar pedidos e provas.
- **Recurso (apelação/inominado)**: tempestividade e preparo/gratuidade → síntese da sentença → razões por tópico → prequestionamento → pedido de reforma específico.
- **Contrarrazões**: inadmissibilidade (se houver) → manutenção da sentença por fundamento.
- **Requerimento e recurso administrativo (INSS/CRPS)**: síntese do pedido e do indeferimento → razões ponto a ponto com documentos e normas → pedido de reforma; recurso à Junta de Recursos no prazo da norma vigente.
- **Embargos de declaração**: omissão/contradição/obscuridade/erro material (art. 1.022 CPC) com o trecho do julgado; sem rediscutir mérito.
- **Trabalhista (inicial)**: pedidos líquidos e com valor (art. 840, § 1º, CLT).

## B4. Redação persuasiva
- Abrir cada seção de fundamentos com a conclusão e só depois desenvolver.
- Ligar **cada fato a uma prova** ("laudo do Dr. X, CRM …, de dd/mm/aaaa — doc. N") e cada tese a lei + precedente obrigatório + norma aplicável.
- Parágrafos curtos (até 6–7 linhas), frases diretas, voz ativa; sem adjetivação vazia nem latinismos desnecessários.
- Precedentes: poucos e fortes, na ordem de força; após cada citação, 2–4 linhas aplicando a tese ao caso.
- Antecipar e neutralizar a defesa do réu — inclusive mostrando quando a própria norma administrativa reconhece o direito.
- Visual Law: recortes dos documentos logo após o parágrafo que os menciona, com os dados essenciais também por escrito no texto. Sem a imagem, usar o bloco `print` (marcador amarelo).
- Pedidos: um por letra, específicos e autossuficientes, com termo inicial, correção e juros, honorários conforme o rito; sucessivos/subsidiários identificados.

---

# PARTE C — GERAR O .DOCX NO MODELO DO ESCRITÓRIO

## C1. Modelo
Usar o .docx indicado em `config/escritorio.json` (cabeçalho, rodapé, margens e estilos do escritório). O modelo precisa ter os estilos Título 2 e Título 3. Sem modelo, **pedir o arquivo** — não recriar cabeçalho/logo do zero.

## C2. Como gerar
1. Escrever o conteúdo como lista JSON de blocos (tipos no cabeçalho de `scripts/gerar_peticao.py`). Negrito inline com `**…**`.
2. Rodar: `python3 scripts/gerar_peticao.py config/escritorio.json conteudo.json SAIDA.docx` (requer `python-docx`).
3. Converter para PDF (`soffice --headless --convert-to pdf SAIDA.docx`) e conferir o layout renderizado. O PDF de protocolo deve ter texto nativo (pesquisável).
4. Rodar `python3 scripts/checa_texto_oculto.py SAIDA.docx`.
5. Nome do arquivo: `AAAA-MM-DD - Tipo da peça - Nome do cliente.docx`.

---

# PARTE D — REVISÃO FINAL (checklist obrigatório)

- [ ] Endereçamento e competência corretos (JF × Estadual × Trabalho; JEF × vara comum pelo valor da causa).
- [ ] Qualificação completa; nenhum `{{CAMPO}}` sem destaque.
- [ ] Datas e números conferidos com os documentos.
- [ ] Cada fato relevante tem prova indicada.
- [ ] Toda jurisprudência no formato A6, conferida no site oficial, com número completo; nenhum tema pendente apresentado como tese firmada.
- [ ] Pedidos ↔ fundamentos; sucessivos/subsidiários; termo inicial; correção e juros; honorários; gratuidade; provas e perícia; tutela; audiência de conciliação (art. 319, VII, CPC).
- [ ] Valor da causa em número e por extenso, coerente com a planilha.
- [ ] Quesitos adaptados ao caso.
- [ ] Prazo processual verificado.
- [ ] Lei, decreto e normas administrativas na redação vigente.
- [ ] Quadro-resumo, títulos descritivos, anexos nomeados e em PDF pesquisável.
- [ ] `checa_texto_oculto.py` sem alertas; layout conferido em PDF.

Entregar junto com o .docx: campos pendentes e documentos faltantes; tabela-resumo dos precedentes (tribunal | força | favorável/desfavorável | conferido sim/[CONFIRMAR]); riscos; lista de anexos e metadados para o peticionamento.

## Regras de ouro
- Só fonte oficial; nada de jurisprudência, norma ou doutrina de memória.
- Nunca inventar fatos, datas, números ou referências.
- Ementa literal, grifo em negrito só no essencial, "(grifei)" ao final.
- Nunca texto oculto nem comandos dirigidos à IA do tribunal (prompt injection) — além de antiético, já gerou multa por litigância de má-fé e ofício à OAB.
