# 온보딩 화면 템플릿

## 화면 목적
- 첫 사용자에게 서비스 가치를 빠르게 전달한다.

## 주요 구성요소
- 가치 소개 슬라이드
- 권한 요청(알림 등)
- 시작하기 CTA

## 상태
- 첫 진입
- 권한 요청 중
- 완료
- 건너뛰기

## 인터랙션
- 다음/이전 슬라이드
- 권한 허용/거부
- 시작하기 버튼

## 데이터 바인딩
| UI 요소 | 데이터 키 | 타입 |
|---|---|---|
| 슬라이드 제목 | `onboarding.slides[i].title` | string |
| 설명 | `onboarding.slides[i].description` | string |

## 이벤트
- `screen_onboarding_view`
- `cta_onboarding_next_click`
- `cta_onboarding_skip_click`
- `onboarding_completed`

## QA 체크리스트
- [ ] 스킵 후 홈 진입
- [ ] 권한 거부 시 대체 안내
