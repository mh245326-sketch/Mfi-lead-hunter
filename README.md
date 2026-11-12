# MFI Lead Hunter AI

Plataforma de prospecção comercial: encontra empresas por segmento e cidade, qualifica os leads, audita sites, gera abordagens e prompts de sites, e organiza tudo em um pipeline.

## Arquivos

| Arquivo | Para que serve |
| --- | --- |
| `index.html` | Aplicativo completo (um único arquivo) |
| `api/brave.js` | Função da Vercel para o Brave Search (opcional) |
| `README.md` | Este guia |

## Como publicar na Vercel

1. Descompacte o ZIP.
2. Envie a pasta `mfi-lead-hunter` para a Vercel (painel, CLI ou repositório no GitHub).
3. Opcional: em **Settings > Environment Variables**, crie `BRAVE_API_KEY` com a sua chave do Brave Search. Sem ela, só a busca de sites pelo Brave deixa de funcionar.

## Como usar sem publicar

Abra o `index.html` no navegador do computador. A busca automática funciona assim também. Dentro do claude.ai ela é bloqueada.

## Funções

- **Prospectar:** escolha ou digite o segmento e as cidades (várias separadas por ponto e vírgula) e clique em **Buscar empresas agora**. Também é possível adicionar manualmente, colar uma lista ou importar CSV.
- **Verificar sites e presença:** PageSpeed nos sites encontrados e Brave Search para localizar possíveis sites e Instagram.
- **Meus leads:** filtros, ficha com fonte e data, exportação e importação em CSV, marcação "Não contatar".
- **Pontuação:** nota de 0 a 100 explicada, com pesos editáveis.
- **Abordagem e prompt do site:** textos montados por modelo, com opção de refinar por IA.
- **Pipeline, Painel e Mapa:** etapas dos leads, indicadores calculados dos seus dados e mapa dos leads.

## Fontes de dados

Nominatim, Photon, Geoapify (com chave) e Overpass/OpenStreetMap para empresas e localização. Google PageSpeed Insights para auditoria. Brave Search (via `api/brave.js`). Leaflet para o mapa. Ollama, Gemini, Groq ou Hugging Face para a IA, com chave opcional.

## Chaves opcionais

Na aba **Pontuação**, em **Fontes e chaves**: Geoapify, PageSpeed e provedor de IA. As chaves ficam só no navegador de quem usa.

## Dados e privacidade

Os leads ficam salvos no navegador. Faça backup em JSON (aba Pontuação) e exporte CSV (aba Meus leads). Informação não encontrada aparece como "Não identificado", e nada é enviado automaticamente a ninguém.

## Limitações

- A cobertura do OpenStreetMap varia de lugar para lugar.
- Serviços gratuitos têm limites de uso, e buscas em muitas cidades seguidas podem falhar por um tempo.
- Estado e País valem para todas as cidades de uma mesma busca.
- Não incluídos: Lighthouse local, Wappalyzer, Common Crawl, GeoNames, Wikipedia, Internet Archive, OSRM, exportação em PDF, análise de concorrentes e fila de busca em lote.
