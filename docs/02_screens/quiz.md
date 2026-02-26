# 가이드 생성 진행 화면 명세 (Generate)

## 화면 목적
- 캡처한 페이지를 Guide로 변환하는 진행 상태를 명확히 안내한다.
- 성공 시 GuideDetail로 즉시 연결한다.

## 주요 구성요소
- 진행 단계 텍스트: `OCR -> 구조화 -> 가이드 생성`
- 로딩 인디케이터
- 실패 시 재시도 버튼
- 완료 시 `가이드 보기` CTA

## 상태
- 생성 요청 접수
- 처리 중
- 완료
- 실패

## 인터랙션
- 완료 시 `가이드 보기` 탭 -> GuideDetail 이동
- 실패 시 재시도
- 취소 시 홈 이동

## 데이터 바인딩
| UI 요소 | 데이터 키 | 타입 | 규칙 |
|---|---|---|---|
| 생성 작업 ID | `generate.jobId` | string | 필수 |
| 상태 | `generate.status` | string | queued/processing/done/failed |
| 결과 가이드 ID | `generate.guideId` | string | done 시 필수 |
| 에러 코드 | `generate.errorCode` | string | failed 시 선택 |

## 이벤트
- `screen_generate_view`
- `generate_started`
- `generate_completed`
- `generate_failed`
- `cta_generate_retry_click`
- `cta_generate_open_guide_click`

## QA 체크리스트
- [ ] 상태 전환 문구 일관성
- [ ] 완료 후 GuideDetail 딥링크 검증
- [ ] 실패 재시도 후 중복 Guide 생성 방지
