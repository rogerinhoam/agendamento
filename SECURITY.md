# Política de segurança

## Supabase

A chave `anon`/`publishable` pode aparecer no frontend. A segurança deve ser aplicada no banco por meio de Row Level Security (RLS). Uma chave `service_role` jamais deve ser enviada ao navegador ou versionada.

Tabelas observadas no aplicativo:

- `appointments`
- `blocked_slots`
- `open_days`
- `services`
- `users`

## Controles mínimos

- Habilite RLS em todas as tabelas acima.
- Permita leitura pública apenas dos campos necessários para escolher serviços e horários.
- Restrinja criação de agendamentos aos campos esperados e valide dados no banco.
- Restrinja atualização e exclusão a usuários autenticados cujo registro em `users` tenha papel administrativo.
- Não confie na verificação de `role` feita somente pelo JavaScript; ela serve para interface, não para autorização.
- Não exponha e-mail de clientes, telefone ou detalhes internos em consultas públicas.
- Revise os logs do Supabase e defina limites contra abuso.

## Se uma credencial privada foi publicada

Revogue-a imediatamente no provedor, gere outra credencial, atualize o serviço e remova o valor do histórico Git. Apenas apagar a linha no commit mais recente não invalida a credencial antiga.

## Relato responsável

Não abra uma issue pública contendo dados pessoais, tokens ou procedimentos de exploração. Entre em contato diretamente com o mantenedor do repositório.
