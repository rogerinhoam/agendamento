# Agendamento

Aplicação web de agendamento com catálogo de serviços, disponibilidade de horários e painel administrativo. O frontend é uma página estática e usa Supabase para autenticação e persistência.

## Tecnologias

- HTML, CSS e JavaScript
- Tailwind CSS via CDN
- Supabase (`supabase-js`)

## Execução local

Sirva a pasta com um servidor HTTP local; abrir o arquivo diretamente pode impedir o funcionamento de módulos e recursos do navegador.

```bash
python -m http.server 8000
```

Depois, acesse `http://localhost:8000`.

## Configuração do Supabase

O navegador precisa conhecer a URL do projeto e uma chave `anon` ou `publishable`. Essas chaves são públicas por definição e **não substituem controle de acesso**.

Antes de publicar:

1. Confirme que a chave usada é `anon`/`publishable`, nunca `service_role`.
2. Habilite Row Level Security (RLS) em todas as tabelas acessadas.
3. Garanta que somente usuários autenticados com papel administrativo possam alterar serviços, horários e agendamentos.
4. Teste as políticas com uma sessão anônima e com uma conta comum.
5. Configure os domínios permitidos e URLs de redirecionamento no Supabase Auth.

Consulte [SECURITY.md](SECURITY.md) antes de usar dados reais.

## Estrutura

- `index.html`: interface, rotas do cliente e integração com Supabase.

## Licença

Adicione uma licença explícita antes de aceitar contribuições externas.
