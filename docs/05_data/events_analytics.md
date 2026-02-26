# 이벤트/분석 템플릿

## 목적
- 사용자 행동을 일관된 이벤트 네이밍으로 수집한다.

## 네이밍 규칙
- 형식: `category_screen_action[_result]`
- category 예시: `screen`, `cta`, `lesson`, `quiz`, `tts`
- 예시:
- `screen_home_view`
- `cta_lesson_save_click`
- `lesson_completed`
- `tts_play_started`

## 필수 공통 파라미터
| 파라미터 | 타입 | 설명 |
|---|---|---|
| `user_id` | string | 사용자 ID |
| `session_id` | string | 세션 ID |
| `screen_name` | string | 현재 화면 |
| `lesson_id` | string | 레슨 ID(해당 시) |
| `timestamp` | string | ISO8601 |

## 핵심 이벤트 카탈로그
### 화면 진입
- `screen_home_view`
- `screen_lesson_view`
- `screen_practice_view`
- `screen_quiz_view`
- `screen_report_view`

### CTA
- `cta_home_start_lesson_click`
- `cta_lesson_next_click`
- `cta_quiz_submit_click`

### 완료
- `lesson_completed`
- `practice_completed`
- `quiz_completed`

### 저장
- `cta_lesson_save_click`
- `saved_removed`

### 재생(TTS)
- `cta_lesson_tts_play_click`
- `tts_play_started`
- `tts_play_failed`
- `tts_play_completed`

## 이벤트 품질 체크리스트
- [ ] 이름 중복/의미 충돌 없음
- [ ] 파라미터 타입 일치
- [ ] PII(개인정보) 비수집 확인
