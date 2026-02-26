# 퀴즈 화면 템플릿

## 화면 목적
- 학습 이해도를 점검하고 점수를 제공한다.

## 주요 구성요소
- 퀴즈 진행 바
- 문제/선택지
- 제출 버튼
- 결과 요약 카드

## 상태
- 시작 전
- 풀이중
- 제출 완료
- 결과 표시
- 오류

## 인터랙션
- 선택지 탭 -> 제출
- 제출 후 정답 공개
- 결과 보기 CTA

## 데이터 바인딩
| UI 요소 | 데이터 키 | 타입 |
|---|---|---|
| 문제 | `quiz.items[i].question` | string |
| 선택지 | `quiz.items[i].choices[]` | array |
| 점수 | `quiz.score` | number |

## 이벤트
- `screen_quiz_view`
- `cta_quiz_submit_click`
- `quiz_question_answered`
- `quiz_completed`

## QA 체크리스트
- [ ] 점수 계산식 검증
- [ ] 중복 제출 방지
