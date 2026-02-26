# 온보딩 화면 명세

## 화면 목적
- 마미버디를 "엄마의 독서 지도 성장 도구"로 명확히 인식시킨다.
- 첫 사용자에게 페이지 기반 Guide 흐름을 빠르게 이해시킨다.

## 핵심 메시지
- 한 페이지를 찍으면 구조화된 Guide가 생성됩니다.
- 질문 중심 읽기(CROW)로 아이와의 대화를 깊게 만듭니다.
- 데이터는 사용자별로 분리 저장되며 공유되지 않습니다.

## 주요 구성요소
- 소개 슬라이드(3~4장)
- 카메라 권한 안내
- 시작하기 CTA

## 상태
- 첫 진입
- 권한 안내
- 완료
- 건너뛰기

## 인터랙션
- 다음/이전
- 건너뛰기
- 시작하기 -> Home 이동

## 데이터 바인딩
| UI 요소 | 데이터 키 | 타입 | 규칙 |
|---|---|---|---|
| 슬라이드 제목 | `onboarding.slides[i].title` | string | 필수 |
| 슬라이드 본문 | `onboarding.slides[i].body` | string | 짧은 문장 |
| 완료 여부 | `onboarding.completed` | boolean | 재노출 제어 |

## 이벤트
- `screen_onboarding_view`
- `cta_onboarding_next_click`
- `cta_onboarding_skip_click`
- `onboarding_completed`

## MVP vs Later
### MVP
- 핵심 가치 안내
- 권한 안내
- Home 진입

### Later
- 사용자 유형별 온보딩 분기

## QA 체크리스트
- [ ] 핵심 메시지 오해 없이 전달
- [ ] 스킵/완료 상태 영속화
- [ ] 권한 거부 후 대체 안내 제공
