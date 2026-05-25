# Mesa Executiva — Nepomuceno Soares Advogados Associados

Site privado de uso restrito aos sócios para tomada de decisões estratégicas. Agrega dados operacionais dos sites do escritório num briefing executivo.

## URL

https://rodsoares88.github.io/mesa-executiva-ns/

## Acesso

Protegido por senha (StatiCrypt). Senha **só dos sócios** — não compartilhar com equipe operacional.

## Estrutura

3 mesas previstas (1 ativa, 2 placeholders):

- **🎯 Mesa Diretora · BMG** (ativa) — análise da carteira BMG com 5 visões executivas (Administrativo, Jurídico, Estratégico, Operacional, Risco) em debate encadeado
- **🏛️ Mesa de Licitações** (placeholder) — análise de editais via `radar-licitacoes` + `radar-analise`
- **📊 Visão Consolidada** (placeholder) — painel agregando todas as mesas

## Fontes de dados (Mesa Diretora · BMG)

Dados embedded no HTML (estratégia de segurança: zero exposição em URL pública):

- `DATA` — 2.091 decisões publicadas (Fev-Mai/26) recalculadas por UF×Causa
- `CARTEIRA_BMG` — estoque oficial BMG 24m (12.250 ações, taxa 39,4%)
- `DECISOES_FINAL` — base completa com tags + alertas
- `RGB_DATA` — 15 segmentos da Régua BMG
- `META_INFO` — snapshot Thais (atualizado manual a cada email)

Quando o Site 1 (`nepomucenoaores-bmg`) processa planilhas novas, esses JSONs precisam ser sincronizados aqui também.

## Re-edição

1. Editar `index.html` (claro · não commitar versão clara)
2. Encriptar:
   ```powershell
   & "npx.cmd" --yes staticrypt index.html -p "Sextante-Cardeal-Mesa-Diretora-2026" --short
   ```
3. Mover `encrypted/index.html` pra raiz (StatiCrypt 3.x sempre cria essa pasta):
   ```powershell
   Move-Item .\encrypted\index.html .\index.html -Force
   Remove-Item .\encrypted -Force
   ```
4. `git add index.html; git commit; git push`

## Histórico

- 2026-05-25 v0.1 · Bootstrap. Mesa Diretora BMG migrada do Site 1 (commit `4e24ca7` do nepomucenoaores-bmg). 2 abas placeholder pra expansão futura.
