# Skills de petições jurídicas para Claude — versão gratuita

Skill para o Claude (Claude.ai, Cowork, Claude Code) que ajuda advogados(as) a:

- **pesquisar jurisprudência consolidada direto nos sites oficiais** (STF, STJ, TNU, TST, TRFs, TJs, TRTs), seguindo a ordem de força do art. 927 do CPC;
- **citar no padrão**: ementa literal, número completo do processo, órgão, relator(a), data, grifo em negrito e "(grifei)" — sem número completo, o julgado não entra;
- **redigir petições** com estrutura clara e redação persuasiva (inicial, réplica, recurso, contrarrazões, embargos, requerimento administrativo);
- **gerar o .docx no modelo do seu escritório** (cabeçalho, rodapé, fonte e assinaturas configuráveis);
- **checar texto oculto** antes do protocolo.

> ⚠️ Ferramenta de apoio. Toda peça deve ser revisada e assinada por advogado(a). Leis, normas e precedentes mudam: a skill manda conferir tudo na fonte oficial, mas a responsabilidade final é de quem assina.

## ⭐ Versão Pro

A versão **Pro** inclui tudo desta versão e mais:

- **Roteiros de todos os benefícios do INSS**, judicial e administrativo (incapacidade, auxílio-acidente, aposentadorias por idade, transição, especial e PcD, BPC/LOAS, pensão por morte, auxílio-reclusão, salário-maternidade, revisões), com requisitos, provas, teses de partida, termo inicial, pedidos e quesitos;
- **Instruções Normativas do INSS vigentes** e como mantê-las atualizadas;
- **Guia de escrita para as ferramentas de IA e automação dos tribunais** e adaptação por tribunal;
- **Skill de protocolos de julgamento do CNJ** (perspectiva de gênero, racial e da pessoa com deficiência), com as diretrizes previdenciárias lidas no texto oficial;
- **Atualizações periódicas** enquanto a assinatura estiver ativa.

👉 **[Link para adquirir a versão Pro]** <!-- substitua pelo link do GitHub Sponsors, Hotmart, Kiwify etc. -->

## Estrutura

```
skills/peticoes-juridicas/
  SKILL.md                    fluxo principal
  references/fontes-oficiais.md
  scripts/gerar_peticao.py    gera o .docx a partir do modelo do escritório
  scripts/checa_texto_oculto.py
config/escritorio.example.json
```

## Como usar

1. Baixe o repositório (*Code → Download ZIP*).
2. Copie `config/escritorio.example.json` para `config/escritorio.json` e preencha com os dados do seu escritório; coloque seu modelo .docx em `modelos/` (fora do Git).
3. Instale a skill:
   - *Claude.ai / Cowork*: **Configurações → Capacidades → Skills**, envie a pasta `skills/peticoes-juridicas` compactada em .zip.
   - *Claude Code*: copie a pasta para `~/.claude/skills/`.
4. Ajuste em `references/fontes-oficiais.md` os tribunais da sua região (os exemplos são da 4ª Região).

Requisitos para gerar o .docx: Python 3 e `pip install python-docx`.

## Privacidade

Não publique `config/escritorio.json`, modelos com logotipo/endereço nem documentos de clientes — o `.gitignore` já os exclui.

## Licença

MIT — veja `LICENSE`. A versão Pro tem licença própria, de uso restrito.
