# 연습 화면 템플릿

## 화면 목적
- 레슨 내용을 짧은 반복 문제로 강화한다.

## 주요 구성요소
- 문제 카드
- 선택지/입력 영역
- 정답 확인 피드백
- 다음 문제 버튼

## 상태
- 로딩
- 풀이중
- 정답/오답 피드백
- 완료
- 오류

## 인터랙션
- 답안 선택/입력
- 제출 -> 즉시 피드백
- 다음 문제 이동

## 데이터 바인딩
| UI 요소 | 데이터 키 | 타입 |
|---|---|---|
| 문제 문장 | `practice.items[i].question` | string |
| 선택지 | `practice.items[i].choices[]` | array |
| 정답 | `practice.items[i].answer` | string |

## 이벤트
- `screen_practice_view`
- `cta_practice_submit_click`
- `practice_answer_result`
- `practice_completed`

## QA 체크리스트
- [ ] 정답/오답 로직 일치
- [ ] 마지막 문제 후 퀴즈 이동
