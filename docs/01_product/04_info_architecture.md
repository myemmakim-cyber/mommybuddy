# 정보구조(IA) 템플릿

## 내비게이션 맵
- 1Depth:
- 홈
- 레슨
- 연습
- 퀴즈
- 저장 라이브러리
- 리포트
- 설정

## 화면 인벤토리
| 화면 ID | 화면명 | 목적 | 진입 경로 | 비고 |
|---|---|---|---|---|
| SCR-HOME | 홈 | 학습 시작 | 앱 시작 | (TODO) |
| SCR-LESSON | 레슨 | 핵심 학습 | 홈 CTA | 카드 스와이프 |
| SCR-PRACTICE | 연습 | 반복 훈련 | 레슨 완료 | (TODO) |
| SCR-QUIZ | 퀴즈 | 이해도 점검 | 연습 완료 | (TODO) |
| SCR-SAVED | 저장 | 재학습 | 홈/설정 | (TODO) |
| SCR-REPORT | 리포트 | 결과 확인 | 퀴즈 완료 | (TODO) |
| SCR-SETTINGS | 설정 | 환경 관리 | 하단 탭 | (TODO) |

## 콘텐츠 계층
- 레슨
- 카드 1: (TODO)
- 카드 2: (TODO)
- 연습 문제: (TODO)
- 퀴즈 문항: (TODO)

## URL/라우트 초안
- `/home`
- `/lesson/:lessonId`
- `/practice/:lessonId`
- `/quiz/:lessonId`
- `/saved`
- `/report/:lessonId`
- `/settings`

## 오픈 이슈
- [ ] 탭 구조 확정 (하단 탭 vs 스택)
- [ ] 뒤로가기 정책 확정
