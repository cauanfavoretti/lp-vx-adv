# VX Consultoria — Advogados

Landing page React + Vite com três seções, layout responsivo e ícones Lucide.

## Executar

```sh
npm install
npm run dev
```

Build: `npm run build`. A hospedagem estática deve redirecionar `/obrigado` para `index.html`.

## Configuração de lançamento

Copie `.env.example` para `.env.local` e configure:

- `VITE_LEAD_ENDPOINT`: endpoint público de captação que aceite POST JSON e CORS. Use um backend/webhook que encaminhe os dados ao GHL. Nunca inclua tokens privados no frontend. O backend deve validar campos, limitar requisições e retornar sucesso apenas após registrar o lead.
- `VITE_META_PIXEL_ID`: ID numérico do pixel. PageView é inicializado na visita; Lead somente em `/obrigado` após envio confirmado, sem repetição no refresh da mesma sessão.
- `VITE_TESTIMONIAL_QUOTE`, `VITE_TESTIMONIAL_NAME`, `VITE_TESTIMONIAL_ROLE`: depoimento real autorizado. Sem estes campos, aparece um espaço claramente identificado como pendente.

Payload: name, phone, email, team_size, practice_area, revenue, consent, source, tracking (UTMs e fbclid). Sem endpoint, o formulário informa indisponibilidade e não simula envio. O formulário inclui estrutura do escritório e principal área de atuação.

Antes do lançamento: inserir logo oficial, depoimento autorizado, endpoint e pixel; revisar o consentimento e a política de privacidade da operação. Validar captação real no GHL e evento no Gerenciador de Eventos.
# lp-vx-adv
