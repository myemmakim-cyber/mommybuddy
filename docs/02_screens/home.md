# 홈 화면 템플릿

## 화면 목적
- 사용자가 오늘의 학습을 바로 시작하게 한다.

## 주요 구성요소
- 상단 인사/진행 요약
- 오늘의 레슨 카드
- 이어하기 CTA
- 저장한 레슨 바로가기

## 상태
- 기본
- 로딩
- 빈 상태(오늘의 레슨 없음)
- 오류

## 인터랙션
- 오늘의 레슨 카드 탭 -> 레슨 화면 이동
- 저장 바로가기 탭 -> 저장 화면 이동

## 데이터 바인딩
| UI 요소 | 데이터 키 | 타입 | 비고 |
|---|---|---|---|
| 인사 문구 | `user.name` | string | TODO |
| 오늘의 제목 | `todayLesson.title` | string | TODO |
| 진행률 | `todayLesson.progress` | number | 0~100 |

## 이벤트
- `screen_home_view`
- `cta_home_start_lesson_click`
- `cta_home_saved_click`

## QA 체크리스트
- [ ] 로딩/오류/빈 상태 구분 표시
- [ ] CTA 탭 영역 44px 이상
