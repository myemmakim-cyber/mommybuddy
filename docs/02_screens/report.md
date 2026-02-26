# 최근 가이드 화면 명세 (Recent)

## 화면 목적
- 최근 생성한 Guide를 빠르게 다시 열어 읽기 흐름을 이어간다.
- 엄마의 독서 지도 실행 기록을 부담 없이 확인한다.

## 주요 구성요소
- 최근 Guide 리스트
- 날짜 필터(최근 7일/30일/전체)
- 항목 메타(생성일, 페이지, 장면 요약)

## 상태
- 기본
- 빈 상태
- 로딩
- 오류

## 인터랙션
- 항목 탭 -> GuideDetail 이동
- 필터 변경

## 데이터 바인딩
| UI 요소 | 데이터 키 | 타입 | 규칙 |
|---|---|---|---|
| 최근 목록 | `recent.guides[]` | array | createdAt desc |
| 생성일 | `recent.guides[i].createdAt` | datetime | 로컬 포맷 |
| 페이지 인덱스 | `recent.guides[i].pageIndex` | number/null | nullable |
| 장면 요약 | `recent.guides[i].content.sceneInsight` | string | 1~2줄 |

## 이벤트
- `screen_recent_view`
- `cta_recent_guide_click`
- `recent_filter_changed`

## MVP vs Later
### MVP
- 최근 Guide 목록
- 날짜 필터

### Later
- 읽기 주제 기반 필터
- 개인 회고 메모 연결

## QA 체크리스트
- [ ] 최신순 정렬 검증
- [ ] 빈 상태에서 가이드 생성 CTA 제공
- [ ] 필터 전환 시 목록 정확성 검증
