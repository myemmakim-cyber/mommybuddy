# 리포트 화면 템플릿

## 화면 목적
- 사용자의 학습 결과를 이해하기 쉽게 요약한다.

## 주요 구성요소
- 점수/완료율 요약
- 강점/보완 포인트
- 다음 학습 추천 CTA

## 상태
- 로딩
- 결과 표시
- 데이터 없음
- 오류

## 인터랙션
- 상세 보기 확장
- 다음 레슨 시작
- 공유(옵션)

## 데이터 바인딩
| UI 요소 | 데이터 키 | 타입 |
|---|---|---|
| 점수 | `report.score` | number |
| 완료율 | `report.completionRate` | number |
| 피드백 | `report.feedback[]` | array |

## 이벤트
- `screen_report_view`
- `cta_report_next_lesson_click`
- `report_shared`

## QA 체크리스트
- [ ] 점수/완료율 표기 단위 통일
- [ ] 데이터 없음 처리
