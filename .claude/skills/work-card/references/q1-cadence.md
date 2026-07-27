# 질문 1: 주기 · 소요

## ASK

```json
AskUserQuestion({
  "questions": [{
    "question": "이 일 얼마나 자주 하세요?",
    "header": "주기",
    "options": [
      {"label": "주 1회", "description": "정해진 요일에"},
      {"label": "주 2~3회", "description": "여러 번"},
      {"label": "매일", "description": "거의 날마다"},
      {"label": "비정기", "description": "생길 때마다"}
    ],
    "multiSelect": false
  }]
})
```

받으면 이어서: **"한 번에 몇 분쯤 걸려요? 대충이면 됩니다."**

⛔ STOP.

## PROBE

"글쎄요"라고 하면:

```
지난번에 이거 하실 때, 시작해서 끝날 때까지 커피 몇 잔 드셨어요?
```

정확한 숫자가 목적이 아니다. **"생각보다 오래 걸리네"를 본인이 느끼는 것**이 목적이다.

## CAPTURE

`주기·소요` 칸: "주 1회 / 약 40분"
