# 저장 항목 화면 명세 (Saved Guides)

## 화면 목적
- 엄마가 다시 보고 싶은 Guide를 모아 재사용한다.
- 대화 준비가 필요한 순간에 즉시 재진입하게 한다.

## 주요 구성요소
- 저장 Guide 목록
- 검색(책 제목/장면 키워드)
- 정렬(최신순 기본)
- 저장 해제 액션

## 상태
- 기본
- 빈 상태
- 로딩
- 오류

## 인터랙션
- 목록 항목 탭 -> GuideDetail 이동
- 저장 해제
- 검색어 입력

## 데이터 바인딩
| UI 요소 | 데이터 키 | 타입 | 규칙 |
|---|---|---|---|
| 저장 목록 | `saved.guides[]` | array | 최신순 기본 |
| 가이드 제목 | `saved.guides[i].content.sceneInsight` | string | 1줄 요약 |
| 페이지 인덱스 | `saved.guides[i].pageIndex` | number/null | nullable |
| 저장 시각 | `saved.guides[i].savedAt` | datetime | 필수 |

## 이벤트
- `screen_saved_guides_view`
- `cta_saved_guide_click`
- `cta_saved_remove_click`
- `saved_search_used`

## QA 체크리스트
- [ ] 저장 해제 즉시 목록 반영
- [ ] 검색 결과 0건 상태 노출
- [ ] GuideDetail 재진입 경로 검증
