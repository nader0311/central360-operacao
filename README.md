# Central Publicação 360 — operação isolada

Repositório operacional da Central 360, separado dos sites hospedados na Netlify. **Não conecte este repositório a Netlify, Vercel ou qualquer plataforma de deploy automático.**

## Estrutura
- `social/central360/queue/`: roteiros e legendas preparados para prévia no Telegram. **Não são autorizações de publicação.**
- `social/central360/media/`: imagens e vídeos gerados pelo bot e aprovados pelo usuário, públicos para acesso pelo Metricool.
- `social/central360/approvals/`: registro de autorização explícita do Telegram.
- `social/central360/acks/`: comprovantes de agendamento ou publicação verificados pelo ChatGPT via Metricool.
- `social/central360/storage-check.json`: teste de permissão de gravação.

## Fluxo
ChatGPT cria a fila → Ubuntu sincroniza e renderiza → Telegram apresenta prévia → usuário aprova → Ubuntu registra no GitHub → ChatGPT agenda pelo Metricool → confirmação de cada rede é registrada no GitHub → Telegram informa o resultado.

**Segurança:** não armazene tokens GitHub, credenciais Telegram, arquivos `.env`, senhas ou informações privadas neste repositório público. O bot Telegram nunca publica nas redes. A fila é imutável depois de enviada para revisão; ajustes exigem nova aprovação. O site comercial continua em `nader0311/dinheiro-organizado-360-site`.

**Estado:** a instalação v0.2.5 no Ubuntu e a validação ponta a ponta ainda precisam ser concluídas. As automações permanecem pausadas até a homologação.
