# 마미버디 제품 개요

## 제품 정체성
- 마미버디는 교육 브랜드다.
- 핵심 미션은 엄마의 독서 지도 역량 성장을 돕는 것이다.
- 핵심 사용자 가치는 아이와의 읽기 시간을 더 깊고 구조적으로 만드는 것이다.

## 제품 포지셔닝
- 포지셔닝: 영어 독서 AI 가이드
- 핵심 단위: `한 페이지 -> 한 Guide`
- 핵심 출력물: Guide (단일 기준 산출물)

## 핵심 철학
- 읽기 지도는 지식 전달보다 대화 설계가 중요하다.
- 가이드는 즉시 실행 가능한 짧은 코칭 문장으로 제공한다.
- 과도한 기능보다 일관된 구조와 재사용성을 우선한다.

## Guide 구조 (고정)
1. Book Info
2. Reading Tips
3. Book Sentences
4. Key Words
5. Extra Phrases
6. CROW-based Questions
7. Parent Strategies

## UI 원칙
- 메인 학습 소비 화면은 세로 스크롤 기반 GuideDetail이다.
- Guide 섹션은 고정 순서로 노출한다.
- 숨김형 섹션, 접기형 소비 흐름은 사용하지 않는다.

## 영어 문장 표시 규칙 (필수)
- 학습 UI에 노출되는 모든 영어 문자열은 아래 포맷을 동일하게 사용한다.

```text
English text
▶ audio
Korean meaning (small, muted)
```

- 적용 대상:
- Book Sentences
- Key Words
- Extra Phrases
- CROW Questions
- Follow-up Questions

- 금지:
- 발음기호
- 발음 표기 텍스트

## 데이터 원칙 (MVP)
- 데이터 모델은 페이지 우선(Page-first)이다.
- 각 Guide는 개별 캡처 페이지를 기준으로 생성/저장한다.
- `bookId`는 MVP에서 nullable로 둔다.

### Guide (요약)
- `id`
- `userId`
- `bookId?`
- `pageIndex?`
- `createdAt`
- `imageUri`
- `ocrText?`
- `content.sceneInsight`
- `content.bookSentences[]`
- `content.keyWords[]`
- `content.crowdQuestions[]`
- `content.extraPhrases[]`
- `content.parentStrategies[]`

### Book (Future-ready)
- `id`
- `userId`
- `title`
- `coverImageUri?`
- `normalizedTitle?`
- `createdAt`

## 개인정보/격리 원칙 (Privacy by Design)
- 멀티테넌트 구조를 사용하되 데이터는 사용자 단위로 완전 격리한다.
- 사용자 간 데이터 교차 노출은 허용하지 않는다.
- 사용자 간 공유 최적화(집단 학습 최적화)를 하지 않는다.
- 공유 데이터셋을 만들지 않는다.
- 외부 책 매칭/검색 DB를 사용하지 않는다.

## MVP 범위
### 포함
- Capture -> Generate -> GuideDetail
- 세로 스크롤 GuideDetail
- 저장 및 최근 Guide 목록
- 오디오 재생(stub 포함)

### 제외
- 외부 도서 매칭/리트리벌
- 사용자 간 콘텐츠 공유
- 사용자 간 결합 개인화

## 이후 확장 (Later)
- AI가 Guide들을 Book 단위로 자동 그룹 제안
- 사용자가 그룹 제안을 수정/재지정(override)
- Book 중심 탐색은 MVP 이후 단계에서 점진 반영

## 콘텐츠 톤
- Calm
- Structured
- Intelligent
- Supportive
- Parent-coach oriented

## 문체 가이드
- 학술적 설명형 문장 지양
- 길고 반복적인 지시 문구 지양
- 실행 가능한 짧은 문장 중심
