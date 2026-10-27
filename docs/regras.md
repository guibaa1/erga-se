# Regras de negócio: Erga-se

Este documento reúne as regras já decididas e as pendências. Ele é a fonte de verdade para o comportamento do app e deve ser atualizado a cada decisão nova.

**Princípio:** o app existe para que a pessoa **não desista**. Toda regra deve favorecer a retomada, nunca o abandono.

---

## 1. Onboarding

1. O usuário cria a conta (ou usa o app localmente, sem login, nas fases iniciais).
2. Escolhe a **duração do plano**: 1 semana, 1 mês, 1 ano ou personalizada.
3. Cria o **personagem**, que começa fraco e desmotivado e evolui com a consistência.

## 2. Rotinas e itens

Uma rotina é composta por **itens**. Cada item tem:

| Campo | Descrição |
|---|---|
| Nome | Ex.: "Beber água" |
| Horário ou intervalo | Ex.: 6h, ou a cada 90 min |
| Tipo de aviso | **Alarme** (toca como despertador) ou **notificação rápida** (apito curto e recorrente) |
| Recorrência | Dias da semana ou todos os dias |
| Obrigatório ou opcional | Define se o item conta para o dia cumprido |
| Castigo | Desafio de redenção em caso de falha |

### Castigo do item
Na criação do item, o app pergunta: **"Se você descumprir esta rotina, qual desafio vai cumprir?"** (ex.: 20 flexões). O usuário pode editar o desafio a qualquer momento, inclusive para torná-lo mais difícil.

## 3. Checklist diário

- Reúne todos os itens previstos para o dia.
- O usuário marca cada item conforme cumpre.
- Serve como registro do dia e base para a ofensiva e o calendário.

## 4. Dia cumprido e dia falho

- **Dia cumprido:** todos os itens **obrigatórios** foram marcados até o fim do dia.
- **Dia falho:** pelo menos um item obrigatório ficou sem marcar.
- Itens **opcionais** concedem XP extra, mas nunca causam falha.
- O **fechamento do dia** ocorre à meia-noite, no fuso horário do usuário, e deve funcionar offline.

## 5. Ofensiva (streak)

- Aumenta em 1 a cada dia cumprido.
- Fica **congelada** enquanto houver castigo pendente (não aumenta e não zera).
- **Zera** se o castigo ficar pendente por **7 dias**. O personagem volta ao estágio inicial, mas o **histórico é sempre mantido**.

## 6. Falha e redenção

1. Ao falhar um dia, o castigo do item falho fica **pendente**.
2. No dia seguinte, o personagem acorda **abalado**, com uma fala do tipo "não consegui, mas vou continuar".
3. O usuário cumpre o castigo e toca em **"Cumpri meu castigo"**.
4. O personagem **volta ao estado normal** e a ofensiva segue.

O cumprimento é baseado na **confiança**: o app não verifica a execução do desafio. O texto e a animação reforçam o compromisso do usuário consigo mesmo.

O castigo deve ser apresentado como **desafio de redenção**, com visual positivo, e não como punição.

## 7. Notificações de cobrança

Enquanto houver castigo pendente, o app notifica às **6h, 12h, 16h, 18h e 22h**.

- As mensagens são motivacionais e personalizadas com o desafio escolhido.
  Ex.: "Erga-se. Você prometeu 20 flexões. Ainda dá tempo."
- O **tom escala** conforme os dias pendentes:

| Dias pendentes | Tom |
|---|---|
| 1 a 2 | Encorajador |
| 3 a 5 | Firme |
| 6 a 7 | Emocional (o personagem pede ajuda) |

- As frases vêm de um banco de mensagens por nível, sorteadas para evitar repetição.
- Ao cumprir o castigo, todas as notificações pendentes são **canceladas imediatamente**.
- O usuário pode ajustar **horários e intensidade** nas configurações.

## 8. Personagem

Estados iniciais previstos:

| Estado | Quando ocorre |
|---|---|
| Inicial (fraco) | Início do plano ou após zerar a ofensiva |
| Normal | Rotina em dia |
| Abalado | Dia falho com castigo pendente |
| Evoluído | Marcos de ofensiva (a definir) |

## 9. Pendências a definir

- [ ] Nome, aparência e opções de personalização do personagem
- [ ] Estágios de evolução e marcos de ofensiva
- [ ] Sistema de XP: valores por item e por dia
- [ ] Castigo por item ou geral quando vários itens falham no mesmo dia
- [ ] O que acontece quando o plano termina (renovar, evoluir, arquivar)
- [ ] Existência de "congelamento de ofensiva" por motivos de força maior (doença, viagem)
- [ ] Regra de fuso horário ao viajar
- [ ] Limites de itens por rotina

## 10. Restrições técnicas que afetam as regras

- **iOS:** não permite alarme de verdade para apps de terceiros (apenas notificações) e limita em 64 as notificações locais agendadas. O app agenda uma janela de poucos dias e reagenda a cada abertura.
- **Android:** alarmes exatos exigem permissão especial, e a otimização de bateria de alguns fabricantes pode atrasar ou bloquear notificações.
- **Desktop:** as notificações só funcionam com o app aberto ou em segundo plano.