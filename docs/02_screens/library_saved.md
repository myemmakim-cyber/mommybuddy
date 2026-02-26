# 라이브러리 화면 명세 (Library)

## 화면 목적
- 사용자의 Guide를 페이지 단위로 저장/탐색한다.
- 다시 읽을 페이지를 빠르게 찾도록 돕는다.

## 핵심 원칙
- MVP에서는 Guide를 페이지 단위로 노출한다.
- Book 단위 자동 그룹핑은 이후 단계에서 제안형으로 확장한다.

## 주요 구성요소
- Guide 목록(최신순)
- 검색(제목/장면 키워드)
- 필터(최근/전체)
- 저장 해제 또는 보관 관리

## 상태
- 기본
- 빈 상태
- 로딩
- 오류

## 인터랙션
- 항목 탭 -> GuideDetail 이동
- 검색어 입력
- 저장 상태 변경

## 데이터 바인딩
| UI 요소 | 데이터 키 | 타입 | 규칙 |
|---|---|---|---|
| 목록 | `library.guides[]` | array | page-based |
| Guide ID | `library.guides[i].id` | string | 필수 |
| 생성일 | `library.guides[i].createdAt` | datetime | 최신순 |
| 책 제목 | `library.guides[i].bookTitle` | string/null | nullable |
| 페이지 인덱스 | `library.guides[i].pageIndex` | number/null | nullable |
| 장면 요약 | `library.guides[i].content.sceneInsight` | string | 1~2줄 |

## 이벤트
- `screen_library_view`
- `cta_library_guide_click`
- `library_search_used`
- `cta_library_save_toggle_click`

## MVP vs Later
### MVP
- 페이지 기반 Guide 리스트
- 검색/재진입

### Later
- AI Book 그룹 제안
- 사용자 그룹 수정(override)

## QA 체크리스트
- [ ] 사용자 소유 Guide만 노출
- [ ] createdAt 정렬 검증
- [ ] Book 정보 nullable 처리 검증
