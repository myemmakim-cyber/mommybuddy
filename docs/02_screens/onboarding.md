# 온보딩 화면 명세

## 화면 목적
- 마미버디의 역할을 "엄마의 영어 독서 가이드"로 명확히 인식시킨다.
- 첫 사용자가 캡처 -> 생성 -> GuideDetail 흐름을 바로 이해하게 한다.

## 핵심 메시지
- 한 페이지를 찍으면 읽기 가이드가 생성됩니다.
- 질문 중심(CROWD)으로 아이와 대화가 확장됩니다.
- 데이터는 사용자별로 분리되어 안전하게 관리됩니다.

## 주요 구성요소
- 3~4장 소개 슬라이드
- 개인정보/데이터 격리 안내
- 시작하기 CTA

## 상태
- 첫 진입
- 권한 안내(카메라)
- 완료
- 건너뛰기

## 인터랙션
- 다음/이전
- 건너뛰기
- 시작하기 -> 홈 이동

## 데이터 바인딩
| UI 요소 | 데이터 키 | 타입 | 규칙 |
|---|---|---|---|
| 슬라이드 타이틀 | `onboarding.slides[i].title` | string | 필수 |
| 슬라이드 본문 | `onboarding.slides[i].body` | string | 짧은 문장 |
| 완료 여부 | `onboarding.completed` | boolean | 재노출 제어 |

## 이벤트
- `screen_onboarding_view`
- `cta_onboarding_next_click`
- `cta_onboarding_skip_click`
- `onboarding_completed`

## QA 체크리스트
- [ ] 첫 진입에서 제품 정의가 오해 없이 전달됨
- [ ] 시작하기 후 홈으로 즉시 이동
- [ ] 스킵/완료 상태 영속화
