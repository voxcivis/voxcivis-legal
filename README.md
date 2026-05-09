# voxcivis-legal

Documentos legais da plataforma VoxCivis · servidos via GitHub Pages em <https://legal.voxcivis.ai>.

## Como atualizar

1. Edite o arquivo `.md` correspondente diretamente neste GitHub (botão "Edit" / lápis)
2. Cole o conteúdo novo · faça commit
3. GitHub Pages re-renderiza automaticamente em ~1 minuto
4. Site `legal.voxcivis.ai/<doc>` mostra a nova versão

## Estrutura

- `index.md` → página inicial em `legal.voxcivis.ai/`
- `termos.md` → `legal.voxcivis.ai/termos`
- `privacidade.md` → `legal.voxcivis.ai/privacidade`
- `cookies.md` → `legal.voxcivis.ai/cookies`
- `etica.md` → `legal.voxcivis.ai/etica`
- `dpo.md` → `legal.voxcivis.ai/dpo`
- `seguranca.md` → `legal.voxcivis.ai/seguranca`

- `_config.yml` → configuração Jekyll/GitHub Pages
- `CNAME` → domínio custom `legal.voxcivis.ai`

## Histórico de versões

Cada commit é uma versão · histórico completo em <https://github.com/SIASLTDA/voxcivis-legal/commits/main>.

Para mostrar ao usuário qual versão ele aceitou: usar o hash do commit do dia em que ele aceitou + retenção do arquivo no banco de dados (tabela `aceites`).
