# 설정 화면 명세

## 화면 목적
- 엄마의 사용 환경과 개인정보 설정을 관리한다.
- 읽기 코칭 경험을 방해하지 않는 최소 설정만 제공한다.

## 주요 구성요소
- 계정 정보
- 언어 설정 (ko/en)
- TTS 설정 (stub 기준 on/off, 속도 옵션)
- 데이터 관리 (내 데이터 보기/삭제 요청)
- 로그아웃

## 상태
- 기본
- 저장 중
- 저장 완료
- 오류

## 인터랙션
- 언어 변경
- TTS 설정 변경
- 데이터 삭제 요청 진입
- 로그아웃

## 데이터 바인딩
| UI 요소 | 데이터 키 | 타입 | 규칙 |
|---|---|---|---|
| 로케일 | `settings.locale` | string | ko/en |
| TTS 사용 여부 | `settings.ttsEnabled` | boolean | 기본 on/off 정책 TODO |
| TTS 속도 | `settings.ttsSpeed` | string | slow/normal/fast |
| 데이터 삭제 상태 | `settings.deleteRequestStatus` | string | none/requested/done |

## 이벤트
- `screen_settings_view`
- `cta_settings_locale_change`
- `cta_settings_tts_toggle_click`
- `cta_settings_data_delete_request_click`
- `cta_settings_logout_click`

## QA 체크리스트
- [ ] 설정 변경 즉시 반영
- [ ] 재실행 후 설정 유지
- [ ] 데이터 삭제 요청 플로우 접근성 문구 검증
