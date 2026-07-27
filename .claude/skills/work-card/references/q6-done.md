# 질문 6: 완료 · 수신자

## ASK

```json
AskUserQuestion({
  "questions": [{
    "question": "뭘 보면 이 일이 끝났다고 하세요?",
    "header": "완료 조건",
    "options": [
      {"label": "문서·파일이 나오면", "description": "산출물이 생김"},
      {"label": "누구한테 보내면", "description": "전달이 끝"},
      {"label": "어딘가에 올리면", "description": "게시가 끝"},
      {"label": "확인 받으면", "description": "승인이 끝"}
    ],
    "multiSelect": false
  }]
})
```

받으면 이어서: **"그거 누구한테 가요?"**

⛔ STOP.

## PROBE

"아무도 안 봐요"라고 하면:

```
그럼 이거 안 하면 누가 아쉬워하세요?
```

아무도 없으면 그것도 발견이다. **아무도 안 보는 일에 매주 시간을 쓰고 있었다는 것** — 카드에 그대로 적는다.

## CAPTURE

`완료·수신자` 칸.
