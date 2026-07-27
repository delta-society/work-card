---
name: day1-start
description: 1회차 — Claude Code를 처음 켜고, 감을 잡고, 내 업무 하나를 고른다. "1회차", "Day 1", "시작" 요청에 사용.
---

# Day 1: 시작합니다

이 스킬이 호출되면 아래 **STOP PROTOCOL**을 반드시 따른다.

---

## STOP PROTOCOL — 절대 위반 금지

> 이 프로토콜이 이 스킬의 최우선 규칙이다. 위반하면 수업이 망가진다.

```
┌─ Phase A (한 턴) ───────────────────────────────────────┐
│ 1. references/ 에서 해당 블록 파일의 EXPLAIN 섹션을 읽는다 │
│ 2. 설명한다                                              │
│ 3. 같은 파일의 EXECUTE 섹션을 읽는다                      │
│ 4. "지금 직접 해보세요"라고 안내한다                       │
│ 5. ⛔ 여기서 반드시 STOP. 턴을 종료한다.                   │
│                                                          │
│ ❌ 절대 하지 않는 것: 확인 질문 출제, CHECK 섹션 읽기       │
│ ❌ 절대 하지 않는 것: AskUserQuestion 호출                 │
│ ❌ 절대 하지 않는 것: "해보셨나요?" 묻기                    │
└──────────────────────────────────────────────────────────┘

  ⬇️ 사용자가 "했어", "완료", "다음"이라고 입력한다

┌─ Phase B (다음 턴) ─────────────────────────────────────┐
│ 1. 같은 파일의 CHECK 섹션을 읽는다                        │
│ 2. AskUserQuestion으로 확인한다                          │
│ 3. 피드백을 준다                                          │
│ 4. 다음 블록으로 갈지 AskUserQuestion으로 묻는다           │
│ 5. ⛔ 다음 블록은 다시 Phase A부터.                        │
└──────────────────────────────────────────────────────────┘
```

### 핵심 금지 사항

1. **Phase A에서 AskUserQuestion을 호출하지 않는다**
2. **Phase A에서 CHECK 섹션을 읽지 않는다**
3. **한 턴에 EXPLAIN + CHECK를 같이 하지 않는다** — 반드시 2턴으로 나눈다
4. **한 번에 한 블록만 진행한다** — references 파일을 미리 여러 개 읽지 않는다

### Phase A 종료 문구

Phase A 마지막에는 반드시 아래를 출력하고 STOP한다.

```
---
👆 위 내용을 직접 해보세요.
끝나면 "완료" 또는 "다음"이라고 입력해주세요.
```

이 문구 뒤에 어떤 도구 호출이나 추가 텍스트도 출력하지 않는다.

---

## References 파일 맵

| 블록 | 파일 | 주제 |
|------|------|------|
| 0 | `references/block0-setup.md` | 터미널 열기 · Claude 켜기 · 첫 대화 |
| 1 | `references/block1-feel.md` | 추측하는 AI vs 질문하는 AI |
| 2 | `references/block2-basics.md` | 명령어를 안 외워도 되는 이유 |
| 3 | `references/block3-pick.md` | 내 업무 하나 고르기 |

> 각 파일은 `## EXPLAIN`, `## EXECUTE`, `## CHECK` 섹션으로 되어 있다.

---

## 오늘 끝나면 손에 남는 것

- 돌아가는 Claude Code 환경
- `work-cards/` 폴더에 시작된 카드 파일 1개 (업무 이름 + 주기 + 시작 신호 + 재료)

## 오늘 하지 않는 것

- 순서·판단 지점 파고들기 → 2회차
- 스킬 만들기 → 3회차

한 번에 하나씩 간다.

---

## 시작

아래 표를 보여주고 AskUserQuestion으로 어디서 시작할지 묻는다.

| 블록 | 주제 |
|------|------|
| 0 | 켜기 — 터미널부터 첫 대화까지 |
| 1 | 감 잡기 — 추측 vs 질문 |
| 2 | 기초 — 명령어 안 외워도 되는 이유 |
| 3 | 내 업무 고르기 |

```json
AskUserQuestion({
  "questions": [{
    "question": "어디서부터 시작할까요?",
    "header": "시작 블록",
    "options": [
      {"label": "Block 0: 켜기", "description": "터미널·Claude·첫 대화"},
      {"label": "Block 1: 감 잡기", "description": "추측하는 AI vs 질문하는 AI"},
      {"label": "Block 2: 기초", "description": "명령어를 안 외워도 되는 이유"},
      {"label": "Block 3: 내 업무", "description": "카드 시작하기"}
    ],
    "multiSelect": false
  }]
})
```

선택 후 → 해당 블록의 Phase A부터.
