# Block 0: 켜기

## EXPLAIN

지금 이 화면이 **터미널**이다. 버튼이 없고 글자만 있는 곳.

버튼이 있는 화면(GUI)은 만든 사람이 준비해둔 것만 할 수 있다. 터미널은 컴퓨터가 할 수 있는 모든 일을 시킬 수 있다. AI에게 일을 맡기려면 이쪽이어야 한다.

**터미널 여는 법**
- Mac: `⌘ + Space` → "터미널" 입력 → Enter
- Windows: 시작 버튼 → "PowerShell" 입력 → Enter

**Output Style 설정** — 로그인이 끝나면 배우는 단계에 맞는 모드로 바꾼다.

```
/config
→ Output style 선택
→ Explanatory 선택
```

Explanatory로 두면 Claude가 무언가를 할 때 왜 그렇게 하는지 함께 설명해준다.

## EXECUTE

순서대로 안내한다.

**1. 터미널에 이렇게 칩니다**

```
claude
```

Claude가 인사하면 성공이다. 로그인하라고 나오면 안내대로 진행한다.

**2. 첫 대화**

```
안녕, 나는 [이름]이고 [하는 일]이야. 나한테 인사해줘
```

**3. Output Style**

```
/config
```
→ Output style → Explanatory

**4. 5분간 아무거나 물어보기**

무엇이든 좋다. 지금은 감을 익히는 시간이다.

## CHECK

```json
AskUserQuestion({
  "questions": [{
    "question": "여기까지 되셨나요?",
    "header": "설치 확인",
    "options": [
      {"label": "다 됐어요", "description": "Block 1로"},
      {"label": "아직 하는 중", "description": "시간이 더 필요함"},
      {"label": "막혔어요", "description": "어디서 막혔는지 알려주세요"}
    ],
    "multiSelect": false
  }]
})
```

"막혔어요"를 고르면 어디서 막혔는지 묻고, 해결한 뒤 다시 확인한다. Block 0은 정답 확인이 아니라 완료 확인이다.
