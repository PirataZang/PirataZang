<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,55:2a1460,100:8b2fff&height=200&section=header&text=Igor%20Fronza&fontSize=56&fontColor=ffffff&fontAlignY=36&desc=Engenheiro%20de%20software%20%C2%B7%20Go%20%C2%B7%20Rust%20%C2%B7%20Laravel%20%C2%B7%20AppSec&descAlignY=58&descSize=17" alt="Igor Fronza, engenheiro de software" />

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=18&pause=1400&color=A259F7&center=true&vCenter=true&width=680&lines=nscope%3A+TUI+em+Rust+para+o+nmap%2C+sem+shell+e+sem+unsafe;Orbia%3A+Ollama%2C+Claude+Code%2C+Gemini+e+Codex+numa+janela;Financer%3A+SaaS+multi-tenant+com+170%2B+testes;DevScope%3A+a+TUI+em+Go+que+eu+uso+todo+dia" alt="nscope, Orbia, Financer e DevScope" />

[![Site](https://img.shields.io/badge/igorfronza.dev.br-0d1117?style=for-the-badge&logo=astro&logoColor=a259f7)](https://www.igorfronza.dev.br/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0d1117?style=for-the-badge&logo=linkedin&logoColor=0A66C2)](https://www.linkedin.com/in/igor-fronza-592796249)
[![E-mail](https://img.shields.io/badge/E--mail-0d1117?style=for-the-badge&logo=gmail&logoColor=EA4335)](mailto:igorfronza20@gmail.com)
[![security.txt](https://img.shields.io/badge/security.txt-0d1117?style=for-the-badge&logo=letsencrypt&logoColor=a259f7)](https://www.igorfronza.dev.br/.well-known/security.txt)

</div>

```console
$ whoami
igor fronza · engenheiro de software · Rio do Sul/SC · remoto para o Brasil todo

$ cat ~/foco
dev          Go, Rust, PHP/Laravel, TypeScript, Vue, Kotlin
arquitetura  SaaS multi-tenant, filas e workers, tudo em container, CI que gera SBOM e proveniência
ia           apps que conversam com LLMs locais e CLIs de agentes, cada um em sandbox
segurança    estudando AppSec; threat model, input não confiável e supply chain já entram no código
```

Escrevo ferramenta de terminal em Go e Rust, sistema web em Laravel e Vue, e app desktop em Tauri. Antes de escrever a primeira linha, defino o que entra como dado não confiável: saída de rede, resposta de LLM, planilha importada, argumento de linha de comando. O resto do projeto parte daí.

---

## Projetos em destaque

<table>
<tr>
<td width="50%" valign="top">

### [nscope](https://github.com/PirataZang/nscope)
<a href="https://github.com/PirataZang/nscope"><img src="https://raw.githubusercontent.com/PirataZang/nscope/main/docs/media/tela-comando.png" alt="nscope mostrando o comando do nmap com cada flag explicada" width="100%" /></a>

TUI para o nmap. Monta o comando, explica cada flag, avisa do risco antes de rodar e mostra hosts e portas num painel navegável. Interface em português.

`Rust` `ratatui` `nmap`

**Segurança:** `#![forbid(unsafe_code)]`, `nmap` chamado com lista de argumentos (sem shell), texto vindo da rede sanitizado contra escape de terminal, temporários em diretório `0700`, release com SHA256SUMS, SBOM CycloneDX e build provenance, `cargo audit` e `cargo deny` no fluxo.

</td>
<td width="50%" valign="top">

### [Orbia](https://github.com/PirataZang/orbia)
<a href="https://github.com/PirataZang/orbia"><img src="https://raw.githubusercontent.com/PirataZang/orbia/main/docs/assets/inicio.png" alt="Orbia listando as IAs encontradas no computador" width="100%" /></a>

App desktop que acha Ollama, Claude Code, Gemini CLI e Codex instalados na máquina e abre todos numa interface de chat com Markdown e imagens. Sem chave de API, sem conta nova.

`Tauri 2` `Rust` `TypeScript` `Ollama`

**Segurança:** resposta do modelo tratada como entrada hostil (DOMPurify + CSP que bloqueia script e imagem externos), cada CLI roda numa pasta vazia por conversa, sem shell, e o Codex em sandbox `read-only`.

</td>
</tr>
<tr>
<td width="50%" valign="top">

### [Financer SaaS](https://github.com/PirataZang/financer-saas)
<a href="https://github.com/PirataZang/financer-saas"><img src="https://raw.githubusercontent.com/PirataZang/financer-saas/main/docs/media/dashboard.gif" alt="Dashboard do Financer com clientes, projetos e gráficos" width="100%" /></a>

SaaS multi-empresa de CRM e financeiro: funil de vendas, portal do cliente, importação de planilha em fila, contratos em PDF, sync com Mercado Pago e bot no Telegram. 7 serviços no Compose, 170+ testes no backend.

`Laravel 13` `Vue 3` `PostgreSQL` `Redis` `grammY`

**Segurança:** isolamento por tenant com global scope e um teste que quebra se uma tabela nova nascer sem `company_id NOT NULL`, permissão declarada por ação, credenciais de integração cifradas em repouso, tokens fora do log de auditoria, portal com login por código e sessão separada.

</td>
<td width="50%" valign="top">

### [DevScope](https://github.com/PirataZang/devscope)
<a href="https://github.com/PirataZang/devscope"><img src="https://raw.githubusercontent.com/PirataZang/devscope/main/docs/media/overview.gif" alt="DevScope descobrindo projetos e abrindo container, Git e CI no terminal" width="100%" /></a>

O "htop dos seus projetos". Descobre os projetos da máquina ou da VPS e junta container, Git, CI, túnel, banco, rotas de API e health check no contexto de cada um. Binário único, sem daemon.

`Go` `Bubble Tea` `Docker` `GitHub Actions`

[![Release](https://img.shields.io/github/v/release/PirataZang/devscope?style=flat-square&color=8b2fff&label=release)](https://github.com/PirataZang/devscope/releases)
[![CI](https://img.shields.io/github/actions/workflow/status/PirataZang/devscope/ci.yml?branch=main&label=CI&style=flat-square)](https://github.com/PirataZang/devscope/actions)
[![Stars](https://img.shields.io/github/stars/PirataZang/devscope?style=flat-square&color=8b2fff)](https://github.com/PirataZang/devscope/stargazers)

</td>
</tr>
</table>

---

<details>
<summary><b>Mais telas desses quatro projetos</b></summary>
<br />

<table>
<tr>
<td width="50%" align="center"><img src="https://raw.githubusercontent.com/PirataZang/devscope/main/docs/media/git.gif" alt="DevScope navegando branches e commits" width="100%" /><br /><sub>DevScope: Git do projeto sem sair do painel</sub></td>
<td width="50%" align="center"><img src="https://raw.githubusercontent.com/PirataZang/devscope/main/docs/images/containers.png" alt="DevScope listando containers com logs e stats" width="100%" /><br /><sub>DevScope: containers com logs e stats</sub></td>
</tr>
<tr>
<td align="center"><img src="https://raw.githubusercontent.com/PirataZang/financer-saas/main/docs/media/importacao.gif" alt="Financer importando planilha de clientes" width="100%" /><br /><sub>Financer: planilha, mapeamento de colunas, revisão e fila</sub></td>
<td align="center"><img src="https://raw.githubusercontent.com/PirataZang/orbia/main/docs/assets/temas.png" alt="Orbia nos temas Roxo, Azul, Branco e Preto" width="100%" /><br /><sub>Orbia: a mesma conversa nos quatro temas</sub></td>
</tr>
</table>

</details>

---

## Segurança no código, com link

Nada aqui é certificação. São controles que estão nos repositórios e dá para conferir.

<div align="center">
<a href="https://github.com/PirataZang/nscope"><img src="https://raw.githubusercontent.com/PirataZang/nscope/main/docs/media/seguranca.gif" alt="nscope explicando cada tipo de alvo e avisando sobre autorização antes de escanear" width="720" /></a>
<br /><sub>O nscope explica o alvo e cobra autorização antes de rodar o nmap.</sub>
</div>

| Controle | Ameaça | Onde |
|---|---|---|
| Processo externo sem shell, argumentos em lista, alvo nunca começa com `-` | injeção de comando e de argumento | [nscope](https://github.com/PirataZang/nscope#segurança-modelo-de-ameaças-resumido), [Orbia](https://github.com/PirataZang/orbia) |
| Banner, hostname e saída de script NSE limpos de ESC, bidi e largura zero | injeção de sequência de escape no terminal | [nscope](https://github.com/PirataZang/nscope) |
| Saída de LLM sanitizada antes de virar HTML, CSP restritiva | XSS via resposta do modelo, exfiltração por imagem | [Orbia](https://github.com/PirataZang/orbia) |
| Agente de IA em pasta vazia, sem shell, Codex `read-only` | agente lendo ou alterando arquivo que não devia | [Orbia](https://github.com/PirataZang/orbia) |
| Teste que falha se tabela de tenant não tiver `company_id` obrigatório | vazamento de dados entre empresas (IDOR entre tenants) | [Financer](https://github.com/PirataZang/financer-saas) |
| Segredo cifrado em repouso, apagado depois do uso, fora do log de auditoria | vazamento de credencial | [Financer](https://github.com/PirataZang/financer-saas) |
| SBOM CycloneDX, SHA256SUMS, build provenance, actions fixadas por SHA | supply chain | [nscope](https://github.com/PirataZang/nscope) |
| Confirmação antes de escanear fora da rede privada, com "Não" como padrão | uso não autorizado | [nscope](https://github.com/PirataZang/nscope) |
| `security.txt` com contato e validade (RFC 9116) | falha reportada sem canal privado | [igorfronza.dev.br](https://www.igorfronza.dev.br/.well-known/security.txt) |

**Estudando agora:** OWASP Top 10 a fundo, hardening de headers do meu site (CSP e HSTS), laboratórios e CTF, e o primeiro write-up público. Quando sair, entra aqui com link.

---

## Como eu decido

- Stack escolhida por quem vai manter daqui a dois anos. Por isso Laravel e Postgres no SaaS, Go e Rust em binário único nas ferramentas.
- Entrega em container. Roda igual na minha máquina, na sua e na VPS, e o repositório é do cliente desde o primeiro commit.
- Teste onde a falha seria silenciosa: isolamento de tenant, importação, permissão.
- Sem dependência nova para o que cabe em cinco linhas. No nscope, cada crate tem a justificativa escrita no README.

---

## IA no fluxo

Uso Claude Code, Ollama, Gemini CLI e Codex no dia a dia, e o Orbia nasceu disso. Trato LLM como componente que recebe e devolve dado não confiável: a saída passa por sanitização, o agente roda com o mínimo de permissão e nada vai para produção sem revisão minha. Não entrego código que eu não saiba explicar linha a linha.

![Claude Code](https://img.shields.io/badge/Claude%20Code-0d1117?style=flat-square&logo=claude&logoColor=D97757)
![Ollama](https://img.shields.io/badge/Ollama-0d1117?style=flat-square&logo=ollama&logoColor=white)
![Gemini CLI](https://img.shields.io/badge/Gemini%20CLI-0d1117?style=flat-square&logo=googlegemini&logoColor=8E75B2)
![Codex](https://img.shields.io/badge/Codex-0d1117?style=flat-square&logo=openai&logoColor=white)

---

## Fora do terminal

<table>
<tr>
<td width="58%" valign="top">

### [Spill](https://github.com/PirataZang/Spill)
<a href="https://github.com/PirataZang/Spill"><img src="https://raw.githubusercontent.com/PirataZang/Spill/main/docs/trio.png" alt="Três cartas do Spill: filme, desafio e você prefere" width="100%" /></a>

App Android de cartas para roda de amigos. Modo Conversa com 300 cartas em 6 baralhos (PT e EN) e Modo Drink +18 com 6 jogos. Offline, sem cadastro, sem anúncio e sem pedir nenhuma permissão. APK nas [releases](https://github.com/PirataZang/Spill/releases/latest).

`Kotlin` `Android`

</td>
<td width="42%" valign="top">

### [botrpg](https://github.com/PirataZang/botrpg)
<a href="https://t.me/RPGSilverBot"><img src="https://raw.githubusercontent.com/PirataZang/botrpg/main/docs/demo.gif" alt="botrpg rolando dados no Telegram" width="100%" /></a>

Bot de D&D 5e em português: dados com vantagem, 77 monstros, 319 feitiços, gerador de dungeon, NPCs e loot. No ar em [@RPGSilverBot](https://t.me/RPGSilverBot).

`Node` `Telegram` `Docker`

</td>
</tr>
</table>

### Sites com sistema dentro

Seis demos completas no meu [portfólio](https://github.com/PirataZang/portfolio), feitas em Astro. Cada uma resolve um problema do nicho, além da vitrine. Clique para abrir no ar.

<table>
<tr>
<td width="33%" align="center"><a href="https://www.igorfronza.dev.br/sites/marmoraria/"><img src="https://raw.githubusercontent.com/PirataZang/portfolio/main/public/demos/marmoraria.webp" alt="Demo Marmoraria" width="100%" /></a><br /><b>Marmoraria</b><br /><sub>comparador de acabamentos e orçamento</sub></td>
<td width="33%" align="center"><a href="https://www.igorfronza.dev.br/sites/arquitetura/"><img src="https://raw.githubusercontent.com/PirataZang/portfolio/main/public/demos/arquitetura.webp" alt="Demo PRUMO" width="100%" /></a><br /><b>PRUMO</b><br /><sub>planta interativa e cena guiada por scroll</sub></td>
<td width="33%" align="center"><a href="https://www.igorfronza.dev.br/sites/pulse/"><img src="https://raw.githubusercontent.com/PirataZang/portfolio/main/public/demos/pulse.webp" alt="Demo PULSE" width="100%" /></a><br /><b>PULSE</b><br /><sub>carrinho, compra simulada e ingresso com QR</sub></td>
</tr>
<tr>
<td align="center"><a href="https://www.igorfronza.dev.br/sites/imobiliaria/"><img src="https://raw.githubusercontent.com/PirataZang/portfolio/main/public/demos/imobiliaria.webp" alt="Demo Meridiano Imóveis" width="100%" /></a><br /><b>Meridiano Imóveis</b><br /><sub>ilustrações geradas no build, sem foto</sub></td>
<td align="center"><a href="https://www.igorfronza.dev.br/sites/barbearia/"><img src="https://raw.githubusercontent.com/PirataZang/portfolio/main/public/demos/barbearia.webp" alt="Demo Daniel's" width="100%" /></a><br /><b>Daniel's</b><br /><sub>agendamento em um toque</sub></td>
<td align="center"><a href="https://www.igorfronza.dev.br/sites/alpine-refresh/"><img src="https://raw.githubusercontent.com/PirataZang/portfolio/main/public/demos/alpine-refresh.webp" alt="Demo Alpine Refresh" width="100%" /></a><br /><b>Alpine Refresh</b><br /><sub>narrativa por scroll com parallax em camadas</sub></td>
</tr>
</table>

### Outros repositórios

| Projeto | Stack | O que é |
|---|---|---|
| [peppercore-admin](https://github.com/PirataZang/peppercore-admin) | `Laravel` `Vue` `Docker` | Painel administrativo com back e front no mesmo Compose. |
| [laravel-sync](https://github.com/PirataZang/laravel-sync) | `Laravel` `Vue` | CRM e ERP: pipelines, auditoria de operação e controle de acesso. |
| [mentor-cli](https://github.com/PirataZang/mentor-cli) | `Node` | Professor de programação dentro do terminal. |

---

## Stack que eu sustento

<div align="center">

[![Stack](https://skillicons.dev/icons?i=go,rust,php,laravel,ts,vue,nuxt,astro,tauri,kotlin,postgres,redis,docker,nginx,linux,githubactions,cloudflare&perline=17&theme=dark)](https://skillicons.dev)

</div>

| Área | Ferramentas |
|---|---|
| Linguagens | Go, Rust, PHP, TypeScript, JavaScript, Kotlin |
| Back-end | Laravel, NestJS, AdonisJS, filas e scheduler, REST |
| Front-end e desktop | Vue 3, Nuxt, Pinia, Astro, Tailwind, Tauri 2 |
| Dados | PostgreSQL, MySQL, Redis |
| Infra | Docker e Compose, nginx, Linux, GitHub Actions, Cloudflare Tunnel |
| Segurança | threat model por projeto, CSP, DOMPurify, SBOM, `cargo audit`, `cargo deny`, nmap |

---

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/PirataZang/PirataZang/output/github-contribution-grid-snake-dark.svg" />
  <img src="https://raw.githubusercontent.com/PirataZang/PirataZang/output/github-contribution-grid-snake.svg" alt="Contribuições no GitHub" />
</picture>

### Contato

Vaga, projeto ou conversa técnica: e-mail ou LinkedIn. Também atendo projeto freelance, com escopo e preço fechados no [site](https://www.igorfronza.dev.br/).

Achou uma falha em algum projeto meu? Escreva para o contato do [`security.txt`](https://www.igorfronza.dev.br/.well-known/security.txt) em vez de abrir issue pública.

[![E-mail](https://img.shields.io/badge/igorfronza20@gmail.com-0d1117?style=for-the-badge&logo=gmail&logoColor=EA4335)](mailto:igorfronza20@gmail.com)
[![LinkedIn](https://img.shields.io/badge/Igor%20Fronza-0d1117?style=for-the-badge&logo=linkedin&logoColor=0A66C2)](https://www.linkedin.com/in/igor-fronza-592796249)

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:8b2fff,45:2a1460,100:0d1117&height=110&section=footer" alt="" />

</div>
