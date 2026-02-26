# 레슨 스키마 템플릿

## 목적
- 레슨 콘텐츠의 최소 공통 구조를 정의한다.

## Lesson JSON Schema (초안)
```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "title": "Lesson",
  "type": "object",
  "required": ["id", "title", "cards", "difficulty", "language"],
  "properties": {
    "id": { "type": "string", "description": "레슨 ID" },
    "title": { "type": "string", "description": "레슨 제목" },
    "summary": { "type": "string", "description": "요약" },
    "difficulty": { "type": "string", "enum": ["beginner", "intermediate", "advanced"] },
    "language": { "type": "string", "enum": ["ko", "en"] },
    "cards": {
      "type": "array",
      "minItems": 2,
      "items": {
        "type": "object",
        "required": ["id", "text"],
        "properties": {
          "id": { "type": "string" },
          "text": { "type": "string" },
          "hint": { "type": "string" },
          "example": { "type": "string" },
          "ttsText": { "type": "string" },
          "ttsUrl": { "type": "string" }
        }
      }
    },
    "quiz": {
      "type": "array",
      "items": {
        "type": "object",
        "required": ["id", "question", "choices", "answer"],
        "properties": {
          "id": { "type": "string" },
          "question": { "type": "string" },
          "choices": { "type": "array", "items": { "type": "string" } },
          "answer": { "type": "string" }
        }
      }
    }
  }
}
```

## 샘플 1 (TODO)
```json
{
  "id": "lesson_todo_001",
  "title": "TODO",
  "summary": "TODO",
  "difficulty": "beginner",
  "language": "ko",
  "cards": [
    { "id": "c1", "text": "TODO", "hint": "TODO" },
    { "id": "c2", "text": "TODO", "hint": "TODO" }
  ],
  "quiz": [
    {
      "id": "q1",
      "question": "TODO",
      "choices": ["TODO", "TODO", "TODO"],
      "answer": "TODO"
    }
  ]
}
```

## 샘플 2 (TODO)
```json
{
  "id": "lesson_todo_002",
  "title": "TODO",
  "summary": "TODO",
  "difficulty": "intermediate",
  "language": "en",
  "cards": [
    { "id": "c1", "text": "TODO", "example": "TODO" },
    { "id": "c2", "text": "TODO", "example": "TODO" }
  ],
  "quiz": [
    {
      "id": "q1",
      "question": "TODO",
      "choices": ["TODO", "TODO", "TODO", "TODO"],
      "answer": "TODO"
    }
  ]
}
```

## 검증 체크리스트
- [ ] `cards` 최소 2장 보장
- [ ] 필수 필드 누락 검증
- [ ] 언어 코드 유효성 검증
