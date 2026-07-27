# Block 0: 구동 — 세 줄이면 됩니다

> 자료 20~21장 대응.

## EXPLAIN

시작 전에 네 가지만 확인한다.

| # | 확인 | 방법 |
|---|------|------|
| 1 | Claude 구독 | Pro / Max / Teams / Enterprise 중 하나 — 로그인 시점에 걸린다 |
| 2 | Claude Code 설치 | 터미널에 `claude` → 인사하면 성공 |
| 3 | Node.js | 터미널에 `npx -v` → 버전이 나오면 OK. 스킬 설치에 필요하다 |
| 4 | GitHub 계정 | 학습 사이트 로그인용. 오늘 실습 자체는 없어도 진행된다 |

**터미널 여는 법**
- Mac: `⌘ + Space` → "터미널" 입력 → Enter
- Windows: 시작 버튼 → "PowerShell" 입력 → Enter

설치가 안 돼 있으면 `claude.ai` 대화창에 이렇게 물어보는 게 가장 안전하다 — 내 환경에 맞는 안내가 나온다.

```
Claude Code 설치하는 방법 알려줘
```

**여기서 막히면 손만 든다.** 설치에 시간 쓰는 건 오늘 목적이 아니다.

### 두 가지를 구분한다

- **터미널에 치는 명령** — 컴퓨터에게 직접 시키는 말. 설치, 실행 같은 것
- **Claude에게 하는 말** — 사람에게 말하듯 하는 요청. `/`로 시작하면 정해진 기능 호출

## EXECUTE

**① 터미널에서 — Claude Code 실행**

```
claude
```

**② 터미널에서 — 학습용 스킬 설치**

```
npx skills add delta-society/work-card --agent claude-code --yes
```

**③ Claude 대화창에서 — 첫 스킬 실행**

```
/day1-start
```

③번은 터미널이 아니라 **Claude와 대화하는 창 안에서** 친다. 가장 많이 헷갈리는 지점이다.

**첫 대화**

```
안녕, 나는 ○○○이고 전략마케팅팀에서 ○○ 업무를 해
```

**설정**

```
/config
```
→ Output style → **Explanatory** 선택. 왜 그렇게 했는지 함께 설명해주는 모드다.

## CHECK

```json
AskUserQuestion({
  "questions": [{
    "question": "여기까지 되셨나요?",
    "header": "구동 확인",
    "options": [
      {"label": "다 됐어요", "description": "Block 1로"},
      {"label": "아직 하는 중", "description": "시간이 더 필요함"},
      {"label": "막혔어요", "description": "어디서 막혔는지 알려주세요"}
    ],
    "multiSelect": false
  }]
})
```

"막혔어요"면 어디서 막혔는지 묻고 해결한 뒤 다시 확인한다. 정답 확인이 아니라 완료 확인이다.
