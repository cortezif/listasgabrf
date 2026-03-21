# Portal GABRF — TRF5 · 3ª Turma

Site de gestão de pauta do Gabinete do Des. Rogério Fialho Moreira.

## Estrutura

```
/
├── index.html                  ← Página principal do portal
├── staticwebapp.config.json    ← Configuração do Azure Static Web Apps
├── sessoes/
│   ├── manifest.json           ← Lista de sessões disponíveis
│   ├── SESSAO_09_04_2026.html  ← Arquivo HTML da sessão (gerado pelo app_ementas.py)
│   └── ...
└── README.md
```

## Como adicionar uma nova sessão

1. Gere o arquivo HTML pelo `app_ementas.py` (botão **⬇ HTML** no viewer)
2. Renomeie o arquivo para o padrão: `SESSAO_DD_MM_AAAA.html`  
   Exemplo: `SESSAO_09_04_2026.html`
3. Coloque o arquivo na pasta `sessoes/`
4. Atualize o arquivo `sessoes/manifest.json` adicionando uma entrada:

```json
{
  "nome": "SESSAO_09_04_2026",
  "arquivo": "SESSAO_09_04_2026.html",
  "tipo": "Virtual",
  "processos": 101,
  "descricao": "Sessão Virtual — 09 de abril de 2026"
}
```

5. Faça o commit e push para o repositório. O Azure sincroniza automaticamente.

## Campos do manifest.json

| Campo | Tipo | Descrição |
|---|---|---|
| `nome` | string | Nome de exibição (sem extensão) |
| `arquivo` | string | Nome do arquivo HTML |
| `tipo` | string | `"Virtual"` ou `"Ordinária"` |
| `processos` | number | Número de processos na sessão |
| `descricao` | string | Descrição curta para exibição |

## URL do Azure

https://thankful-water-09e84730f.2.azurestaticapps.net/
