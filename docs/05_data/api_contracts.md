# API 계약 템플릿

## 공통
- Base URL: `/api/v1` (TODO)
- 인증: `Authorization: Bearer (TODO)`
- 응답 형식: JSON

## 1) today-lesson 조회
### Request
```http
GET /api/v1/today-lesson?locale=ko
```

### Response 200 (예시)
```json
{
  "lesson": {
    "id": "lesson_001",
    "title": "TODO",
    "difficulty": "beginner",
    "cards": [
      { "id": "c1", "text": "TODO", "ttsUrl": "TODO" },
      { "id": "c2", "text": "TODO", "ttsUrl": "TODO" }
    ]
  }
}
```

## 2) 레슨 완료 처리
### Request
```http
POST /api/v1/lessons/{lessonId}/complete
Content-Type: application/json

{
  "score": 80,
  "completedAt": "TODO"
}
```

### Response 200 (예시)
```json
{
  "ok": true,
  "progressId": "progress_001"
}
```

## 3) 레슨 저장/해제
### 저장 Request
```http
POST /api/v1/saved
Content-Type: application/json

{
  "lessonId": "lesson_001"
}
```

### 저장 Response 201 (예시)
```json
{
  "savedId": "saved_001",
  "savedAt": "TODO"
}
```

### 해제 Request
```http
DELETE /api/v1/saved/{lessonId}
```

### 해제 Response 200 (예시)
```json
{
  "ok": true
}
```

## 4) TTS 생성 요청
### Request
```http
POST /api/v1/tts/jobs
Content-Type: application/json

{
  "lessonId": "lesson_001",
  "cardId": "c1",
  "text": "TODO",
  "voice": "TODO"
}
```

### Response 202 (예시)
```json
{
  "jobId": "tts_001",
  "status": "queued"
}
```

## 에러 포맷
```json
{
  "error": {
    "code": "TODO_CODE",
    "message": "TODO message"
  }
}
```

## 체크리스트
- [ ] 상태코드 일관성
- [ ] idempotency 필요 API 정의
- [ ] 인증/권한 오류 케이스 정의
