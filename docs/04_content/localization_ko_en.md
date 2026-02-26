# ko/en 로컬라이제이션 템플릿

## 목적
- 한국어/영어 UI와 콘텐츠를 일관되게 운영한다.

## 키 관리 규칙
- 키 형식: `screen.section.element.action`
- 예시:
- `home.header.greeting`
- `lesson.cta.next`
- `quiz.result.title`

## 번역 가이드
- 한국어: 간결하고 존중 표현 사용
- 영어: plain English 우선
- 금지: 직역으로 의미 왜곡되는 표현

## 용어 통일 표
| 키 | ko | en | 비고 |
|---|---|---|---|
| `common.start` | 시작하기 | Start | TODO |
| `common.next` | 다음 | Next | TODO |
| `lesson.save` | 저장 | Save | TODO |

## QA 체크리스트
- [ ] 길이 차이로 레이아웃 깨짐 없음
- [ ] 숫자/날짜 포맷 로케일 반영
- [ ] 폴백 언어 정책 정의

## 미정 항목
- [ ] 존댓말/반말 톤 최종 확정
- [ ] 지역별 영어 변형(US/UK) 정책
