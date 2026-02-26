# 홈 화면 명세 (Guide Home)

## 화면 목적
- 엄마가 페이지 캡처를 즉시 시작하도록 돕는다.
- 최근 생성 가이드와 저장 항목으로 빠르게 재진입하게 한다.

## 핵심 UX 원칙
- 첫 액션은 `페이지 촬영/업로드`로 단순화한다.
- 학습 성취 배지/점수/레벨 요소는 노출하지 않는다.
- 엄마 코치 관점의 조용한 정보 밀도를 유지한다.

## 주요 구성요소
- 상단 헤더: 인사 + 오늘의 읽기 안내
- 메인 CTA: `페이지 찍고 가이드 만들기`
- 최근 가이드 섹션: 최근 N개
- 저장 항목 바로가기
- 하단 보조 영역: 개인정보/가이드 원칙 링크

## 상태
- 기본
- 로딩
- 최근 가이드 없음(Empty)
- 오류(네트워크/조회 실패)

## 인터랙션
- 메인 CTA 탭 -> 캡처 화면 이동
- 최근 가이드 항목 탭 -> GuideDetail 이동
- 저장 바로가기 탭 -> 저장 라이브러리 이동

## 데이터 바인딩
| UI 요소 | 데이터 키 | 타입 | 규칙 |
|---|---|---|---|
| 사용자 이름 | `user.name` | string | 선택 |
| 최근 가이드 목록 | `recentGuides[]` | array | createdAt desc |
| 첫 문장 미리보기 | `recentGuides[i].content.sceneInsight` | string | 1~2줄 제한 |
| 저장 개수 | `saved.total` | number | 0 이상 |

## 이벤트
- `screen_home_view`
- `cta_home_capture_click`
- `cta_home_recent_guide_click`
- `cta_home_saved_click`

## QA 체크리스트
- [ ] 진입 후 1탭 내 캡처 시작 가능
- [ ] Empty 상태에서 메인 CTA 강조 유지
- [ ] 최근 가이드 정렬(createdAt desc) 검증
