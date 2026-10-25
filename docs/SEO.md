# Guia de SEO do site da Dra. Eliane Bezerra

## Estado e regra de domínio

O domínio final ainda não foi definido nem conectado ao projeto Vercel. A versão atual da branch `lancamento-crivo` é uma prévia; não deve ser usada como URL canônica nem enviada ao Google Search Console.

Antes de publicar os arquivos de indexação, confirmar um domínio público e estável, conectá-lo ao projeto Vercel e decidir a versão canônica (com ou sem `www`). Redirecionar as variações HTTP/HTTPS e `www`/apex para uma única versão HTTPS. Só então substituir `DOMINIO_OFICIAL` por essa origem, por exemplo `https://www.exemplo.com.br`.

## Preferências da Dra. Eliane

- Não exibir telefone como canal de atendimento psicológico e não incluir propriedade `telephone` nos dados estruturados. O botão de agendamento deve levar à Doctoralia: https://www.doctoralia.com.br/eliane-bezerra/psicologo/gravata2?saasonly=true
- Não tratar números de telefone do perfil Doctoralia como telefone de atendimento do site.
- Manter endereço, registro profissional, áreas de atuação e demais dados estruturados apenas quando estiverem confirmados e coerentes com o conteúdo visível.
- Não publicar avaliações de pacientes no site sem autorização e revisão ética apropriadas.

## Pendências técnicas encontradas

- A home tem `rel="canonical"` relativo (`/`). Depois de confirmar o domínio, torná-lo absoluto.
- A página `/curso/` tem título e meta description, mas precisa de canonical absoluto e metadados Open Graph/Twitter próprios.
- Ainda não há `robots.txt`, `sitemap.xml` nem `llms.txt` no repositório.
- Não adicionar `meta name="keywords"`: o Google Search não usa esse campo para indexação ou ranqueamento. Usar termos relevantes naturalmente em títulos, subtítulos, texto visível e descrições de página.

## Sequência depois da escolha do domínio

1. Conectar o domínio oficial ao Vercel e confirmar DNS, HTTPS e redirecionamentos.
2. Definir canonicals absolutos para as páginas públicas: `/`, `/curso/`, `/privacidade/`, `/termos/`, `/cookies/` e `/reembolso/`.
3. Criar `robots.txt` permitindo rastreamento das páginas públicas e indicando `https://DOMINIO_OFICIAL/sitemap.xml`.
4. Criar `sitemap.xml` com URLs absolutas do domínio canônico e apenas páginas públicas que respondam corretamente. Não listar previews, URLs de login, parâmetros de campanha ou páginas com `noindex`.
5. Criar opcionalmente `llms.txt` com uma descrição factual do site e links canônicos. É uma convenção emergente para ferramentas de IA; não substitui robots/sitemap e não é promessa de ranqueamento no Google.
6. Completar Open Graph/Twitter na home e no curso, com título, descrição e imagem de compartilhamento adequados a cada página.
7. Verificar o domínio no Google Search Console, enviar o sitemap e inspecionar as páginas principais após a publicação pública.
8. Repetir PageSpeed Insights em mobile e desktop na URL pública e acompanhar os Core Web Vitals. O preview atual tem proteção Vercel; PageSpeed redireciona para a autenticação e não mede corretamente esse preview.

## Referências de performance já coletadas

PageSpeed Insights mobile do endereço estável Vercel (versão anterior à prévia atual), em 24/10/2026: desempenho 69, FCP 3,2 s, LCP 13,5 s, CLS 0. A imagem principal de 1600 px transferia 2.131,7 KiB; o relatório estimou economia de 2.031 KiB com melhor entrega da imagem. Também apontou fontes Google no caminho crítico de renderização. A branch atual reduz a imagem principal para 1000 px e carrega as fontes sem bloquear a primeira renderização; é necessário medir novamente na URL pública depois de definir domínio e publicar.

Relatório: https://pagespeed.web.dev/analysis/https-draelianebezerra-vercel-app/h1vlafa7gg?form_factor=mobile

## Referências oficiais

- Google sobre meta tags suportadas e `meta keywords`: https://developers.google.com/search/docs/crawling-indexing/special-tags
- Google sobre sitemap com URLs absolutas: https://developers.google.com/search/docs/crawling-indexing/sitemaps/build-sitemap
- Google sobre URLs canônicas: https://developers.google.com/search/docs/crawling-indexing/consolidate-duplicate-urls
- Google sobre snippets e meta descriptions: https://developers.google.com/search/docs/appearance/snippet
- Web Vitals: https://web.dev/articles/vitals
