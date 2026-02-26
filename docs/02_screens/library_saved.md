# 저장 라이브러리 화면 템플릿

## 화면 목적
- 사용자가 저장한 레슨을 재학습하게 한다.

## 주요 구성요소
- 저장 목록
- 정렬/필터
- 검색
- 저장 해제 액션

## 상태
- 기본
- 빈 상태
- 로딩
- 오류

## 인터랙션
- 항목 탭 -> 레슨 재진입
- 저장 해제
- 검색 입력

## 데이터 바인딩
| UI 요소 | 데이터 키 | 타입 |
|---|---|---|
| 목록 | `saved.items[]` | array |
| 총 개수 | `saved.total` | number |
| 마지막 저장일 | `saved.items[i].savedAt` | datetime |

## 이벤트
- `screen_saved_view`
- `cta_saved_item_click`
- `cta_saved_remove_click`
- `saved_search_used`

## QA 체크리스트
- [ ] 빈 상태 카피 노출
- [ ] 저장 해제 즉시 반영
