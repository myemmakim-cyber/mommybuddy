# 생성 화면 명세 (Generate)

## 화면 목적
- 페이지 입력을 Guide로 변환하는 진행 상태를 명확히 안내한다.
- 완료 후 GuideDetail로 자동/즉시 이동시킨다.

## 주요 구성요소
- 진행 단계 문구: `OCR -> 구조화 -> Guide 생성`
- 로딩 인디케이터
- 실패 메시지 + 재시도
- 완료 CTA: `가이드 보기`

## 상태
- 요청 접수
- 처리 중
- 완료
- 실패

## 인터랙션
- 완료 -> `가이드 보기` 탭 -> GuideDetail 이동
- 실패 -> 재시도
- 취소 -> Home 이동

## 데이터 바인딩
| UI 요소 | 데이터 키 | 타입 | 규칙 |
|---|---|---|---|
| 작업 ID | `generate.jobId` | string | 필수 |
| 상태 | `generate.status` | string | queued/processing/done/failed |
| 결과 Guide ID | `generate.guideId` | string | done 시 필수 |
| 오류 코드 | `generate.errorCode` | string | failed 시 선택 |

## 이벤트
- `screen_generate_view`
- `generate_started`
- `generate_completed`
- `generate_failed`
- `cta_generate_retry_click`
- `cta_generate_open_guide_click`

## MVP vs Later
### MVP
- 생성 진행 상태 표시
- 완료 후 GuideDetail 연결
- 실패 재시도

### Later
- 단계별 예상 소요 시간
- 백그라운드 생성 알림

## QA 체크리스트
- [ ] 완료 시 GuideDetail 이동 검증
- [ ] 실패 재시도 시 중복 생성 방지
- [ ] 상태 문구 일관성 검증
