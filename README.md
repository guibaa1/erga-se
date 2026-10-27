# Erga-se

> Cair faz parte. Ficar no chão é escolha.

**Erga-se** é um aplicativo de rotina e disciplina que combina lembretes, calendário e gamificação. Você define sua rotina (acordar, beber água, treinar, estudar, tarefas de casa), o app te cobra ao longo do dia e um personagem criado por você evolui junto com a sua consistência.

Quando você falha, o app não te abandona nem te pune: você assume um **desafio de redenção** que você mesmo definiu, e o personagem se levanta de novo.

> **Status:** em planejamento (Fase 0). Ainda não há versão utilizável.

---

## Ideia central

- **Rotinas com avisos de dois tipos:** alarme (ex.: acordar às 6h) e notificação rápida e recorrente (ex.: beber 500 ml de água a cada 90 min).
- **Plano com duração definida:** 1 semana, 1 mês, 1 ano, escolhido no primeiro acesso.
- **Checklist diário** com todos os itens da rotina.
- **Ofensiva (streak)** de dias consecutivos cumpridos.
- **Personagem que evolui** com o usuário e reage ao seu desempenho.
- **Castigo de redenção:** ao falhar, o usuário cumpre um desafio que ele mesmo definiu (ex.: 20 flexões) para retomar a ofensiva.
- **Cobrança insistente e motivacional** enquanto houver castigo pendente (6h, 12h, 16h, 18h e 22h).

As regras completas estão em [`docs/regras.md`](docs/regras.md).

## Plataformas

Android (prioridade), iOS, Windows e Web, a partir de um único código.

## Stack

| Camada | Tecnologia |
|---|---|
| App | Flutter + Dart |
| Estado | Riverpod |
| Navegação | go_router |
| Banco local | SQLite com Drift |
| Notificações | flutter_local_notifications |
| Personagem animado | Rive |
| API (Fase 4) | ASP.NET Core 10 (C#) |
| Banco do servidor (Fase 4) | PostgreSQL + EF Core |
| CI | GitHub Actions |

O app é **offline primeiro**: rotinas, notificações e ofensiva funcionam no próprio aparelho. O backend entra depois, para login e sincronização entre dispositivos.

## Roadmap

- [ ] **Fase 0:** requisitos, regras de negócio, wireframes e repositório
- [ ] **Fase 1 (MVP):** cadastro de rotinas, notificações locais e checklist diário, tudo local
- [ ] **Fase 2:** calendário, ofensiva, XP e fechamento do dia
- [ ] **Fase 3:** personagem, estados emocionais, castigo de redenção e evolução
- [ ] **Fase 4:** API, login e sincronização entre dispositivos
- [ ] **Fase 5:** testes, polimento e publicação nas lojas

## Estrutura do repositório

```
erga-se/
├── app/            # aplicativo Flutter
├── api/            # API ASP.NET Core (Fase 4)
├── docs/           # requisitos, regras de negócio e wireframes
├── .github/        # workflows de CI e templates
└── README.md
```

## Como rodar

_Será documentado quando o projeto Flutter for criado._

## Convenções

**Commits** seguem o padrão [Conventional Commits](https://www.conventionalcommits.org/pt-br/):

```
feat: adiciona cadastro de rotina
fix: corrige reagendamento de notificações
docs: documenta regras da ofensiva
chore: configura análise estática do Dart
```

**Branches:** `main` é sempre estável. Cada tarefa tem uma branch curta, como `feat/checklist-diario` ou `fix/notificacao-ios`, integrada por Pull Request.

## Licença

A definir.