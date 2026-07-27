# 질문 2: 시작 신호

## ASK

```json
AskUserQuestion({
  "questions": [{
    "question": "뭘 보면 '아 이거 해야겠다' 하세요?",
    "header": "시작 신호",
    "options": [
      {"label": "요일·시각이 되면", "description": "달력이 트리거"},
      {"label": "누가 요청하면", "description": "사람이 트리거"},
      {"label": "뭔가 쌓이면", "description": "양이 트리거"},
      {"label": "그냥 내가 챙겨야 함", "description": "트리거 없음 — 기억에 의존"}
    ],
    "multiSelect": false
  }]
})
```

⛔ STOP.

## PROBE

4번(그냥 내가 챙겨야 함)을 골랐으면 한 번 더:

```
그럼 깜빡한 적도 있으세요? 그때 어떻게 아셨어요?
```

**깜빡한 경험이 있으면 그 자체가 자동화 1순위 신호다.** 카드에 적어둔다.

## CAPTURE

`시작 신호` 칸. 4번이었으면 뒤에 `(누락 경험 있음)` 표시.
