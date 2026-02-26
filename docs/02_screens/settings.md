# 설정 화면 템플릿

## 화면 목적
- 계정/알림/언어/접근성 설정을 관리한다.

## 주요 구성요소
- 프로필 요약
- 알림 토글
- 언어 선택(ko/en)
- 접근성 옵션
- 로그아웃

## 상태
- 기본
- 저장중
- 저장 완료
- 오류

## 인터랙션
- 토글 변경
- 언어 변경
- 로그아웃 확인 모달

## 데이터 바인딩
| UI 요소 | 데이터 키 | 타입 |
|---|---|---|
| 알림 설정 | `settings.notifications.enabled` | boolean |
| 언어 | `settings.locale` | string |
| 접근성 옵션 | `settings.a11y` | object |

## 이벤트
- `screen_settings_view`
- `cta_settings_toggle_click`
- `cta_settings_locale_change`
- `cta_settings_logout_click`

## QA 체크리스트
- [ ] 설정 변경 영속화
- [ ] 언어 전환 즉시 반영
