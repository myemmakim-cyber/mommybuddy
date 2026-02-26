# 홈 화면 명세 (Home)

## 화면 목적
- 엄마가 즉시 페이지 캡처를 시작하게 한다.
- 최근 Guide 재진입 경로를 짧게 제공한다.

## 핵심 UX
- 첫 화면의 1순위 CTA는 `가이드 만들기`다.
- 최근 Guide 목록은 재사용성을 높이기 위한 보조 영역이다.
- 교육 브랜드 톤을 유지하기 위해 자극적 요소 없이 차분한 정보 구조를 사용한다.

## 주요 구성요소
- 상단: 환영 문구 + 오늘의 읽기 안내
- 메인 CTA: `페이지 찍고 가이드 만들기`
- 최근 Guide 목록(최신순)
- 저장 Guide 바로가기
- 마이페이지 바로가기

## 상태
- 기본
- 로딩
- 최근 Guide 없음
- 오류

## 인터랙션
- `가이드 만들기` 탭 -> Capture 이동
- 최근 Guide 항목 탭 -> GuideDetail 이동
- 저장 Guide 탭 -> Library 이동
- 마이페이지 탭 -> MyPage 이동

## 데이터 바인딩
| UI 요소 | 데이터 키 | 타입 | 규칙 |
|---|---|---|---|
| 사용자 이름 | `user.name` | string | 선택 |
| 최근 Guide 목록 | `recentGuides[]` | array | createdAt desc |
| 장면 요약 미리보기 | `recentGuides[i].content.sceneInsight` | string | 1~2줄 |
| 생성일 | `recentGuides[i].createdAt` | datetime | 로컬 포맷 |

## 이벤트
- `screen_home_view`
- `cta_home_create_guide_click`
- `cta_home_recent_guide_click`
- `cta_home_library_click`
- `cta_home_mypage_click`

## MVP vs Later
### MVP
- 가이드 생성 CTA
- 최근 Guide 목록
- 저장/마이페이지 진입

### Later
- 개인 읽기 루틴 추천
- 시간대별 읽기 제안

## QA 체크리스트
- [ ] 홈 진입 후 1탭 내 가이드 생성 가능
- [ ] 최근 목록 정렬(createdAt desc) 검증
- [ ] 목록 0건 상태에서 CTA 유지
