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

- `VITE_LEAD_ENDPOINT` (opcional): sobrescreve o endpoint de captação. Sem ele, o formulário envia para o Inbound Webhook do workflow "LP Advogados - Formulário do site (inbound webhook)" no GHL (subconta VX Consultoria), definido em `src/main.jsx`. Nunca inclua tokens privados no frontend.
- `VITE_META_PIXEL_ID`: ID numérico do pixel. PageView é inicializado na visita; Lead somente em `/obrigado` após envio confirmado, sem repetição no refresh da mesma sessão.
- `VITE_TESTIMONIAL_QUOTE`, `VITE_TESTIMONIAL_NAME`, `VITE_TESTIMONIAL_ROLE`: depoimento real autorizado. Sem estes campos, aparece um espaço claramente identificado como pendente.

Payload: name, first_name, last_name, phone (E.164, +55), email, team_size, practice_area, revenue, consent, source, page_url, utm_source, utm_medium, utm_campaign, utm_content, utm_term, fbclid.

Antes do lançamento: inserir logo oficial, depoimento autorizado, endpoint e pixel; revisar o consentimento e a política de privacidade da operação. Validar captação real no GHL e evento no Gerenciador de Eventos.
# lp-vx-adv
