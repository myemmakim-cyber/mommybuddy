# 최근 가이드 화면 명세 (Recent Guides)

## 화면 목적
- 최근 생성된 Guide를 시간순으로 빠르게 다시 연다.
- 엄마가 연속 읽기 세션을 이어가도록 지원한다.

## 주요 구성요소
- 최근 Guide 리스트
- 카드 메타: 생성일, 페이지 인덱스, 장면 요약
- 필터(최근 7일/30일/전체)

## 상태
- 기본
- 빈 상태
- 로딩
- 오류

## 인터랙션
- 항목 탭 -> GuideDetail 이동
- 필터 변경
- 항목 길게 누르기(저장/삭제 메뉴, 선택)

## 데이터 바인딩
| UI 요소 | 데이터 키 | 타입 | 규칙 |
|---|---|---|---|
| 최근 목록 | `recentGuides[]` | array | createdAt desc |
| 생성일 | `recentGuides[i].createdAt` | datetime | 로컬 포맷 |
| 페이지 인덱스 | `recentGuides[i].pageIndex` | number/null | nullable |
| 책 제목 | `recentGuides[i].bookTitle` | string/null | nullable |

## 이벤트
- `screen_recent_guides_view`
- `cta_recent_guide_click`
- `recent_filter_changed`
- `cta_recent_save_click`

## QA 체크리스트
- [ ] createdAt 기준 정렬 정확성
- [ ] 필터 전환 시 성능 저하 없음
- [ ] Empty 상태에서 캡처 CTA 제공
