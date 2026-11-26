# Workflow: Qualificação de lead / Lead qualification
## Objetivo
Receber um lead via webhook, validar o contrato mínimo e devolver uma classificação explicável. O fluxo é determinístico para permitir revisão antes de conectar IA, CRM ou atendimento.
## Entrada
`POST /webhook/inova-lead-qualification`
Campos obrigatórios: `nome`, `email`, `interesse`, `mensagem`. O e-mail deve ter formato válido.
## Saída
`200` com `status`, `prioridade`, `categoria` e `proxima_acao`; `400` com erro de validação. Não armazena dados.
## Produção segura
Proteja o webhook, aplique rate limiting, conecte um destino aprovado e masque dados pessoais nos logs. Para integrar um LLM, envie somente campos mínimos e use credenciais do n8n.
## Teste
`curl -X POST "$N8N_WEBHOOK_URL" -H 'Content-Type: application/json' -d '{"nome":"Ana","email":"ana@example.com","interesse":"automação","mensagem":"Quero integrar atendimento e CRM"}'`
