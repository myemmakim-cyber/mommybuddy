# 마미버디 제품 개요

## 제품 정의
- 앱 이름: 마미버디
- 포지셔닝: 영어 독서 AI 가이드
- 핵심 대상: 아이와 영어책을 읽는 엄마
- 핵심 목표: 엄마가 더 나은 읽기 가이드가 되도록 돕는다.

## 제품 원칙
- 한 페이지 입력에서 하나의 Guide를 안정적으로 만든다.
- 읽기 이해와 부모-아이 대화 확장을 최우선에 둔다.
- 단순하고 조용한 정보 구조를 유지한다.
- 보상형 자극보다 실행 가능한 코칭 문장을 제공한다.

## 핵심 가치
- 한 페이지를 찍으면 즉시 읽기 가이드를 만든다.
- 엄마가 아이와 대화할 수 있는 질문 흐름을 제공한다.
- 단순 설명보다 현장 사용 가능한 코칭 문장을 제공한다.

## 코어 출력 모델
- 원칙: `One captured page -> One Guide`
- Guide는 단일 핵심 출력물이다.
- Guide 구조는 고정이며, 페이지마다 내용만 바뀐다.

### Guide 고정 구조
1. 이 장면의 핵심 (Scene Insight)
2. 책 속 문장 (Book Sentences)
3. 핵심 단어 (Key Words)
4. 아이와 함께 대화해보세요 (CROWD-based Questions)
5. 함께 말해보세요 (Supporting speaking prompts)
6. 엄마표 영어 Tip (Parent Strategy)

## UX 구조 (세로 스크롤 고정)
- 콘텐츠는 모두 세로 스크롤로 노출한다.
- 숨김 섹션과 접기형 인터랙션을 사용하지 않는다.

### GuideDetail 표시 순서
1. Header (Back + "학습 가이드")
2. Book Info
3. Scene Insight
4. Book Sentences
5. Key Words
6. CROW Questions
7. Supporting Phrases
8. Parent Tips

## 문장 표시 규칙 (필수)
- 학습 화면의 모든 영어 문장은 아래 형식으로 렌더링한다.

```text
English sentence
▶ (audio button)
Korean meaning below (muted text)
```

- 적용 대상:
- Book Sentences
- CROW Questions
- Follow-up Questions
- Supporting Phrases
- Key Words

- 금지:
- 발음기호 표기
- 한글 발음 표기

## 데이터 모델 원칙 (페이지 우선)
- Guide 중심으로 저장한다.
- MVP에서는 `bookId`를 nullable로 유지한다.
- 미래에는 Guide를 Book으로 자동 그룹핑한다.

### Guide 스키마 요약
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

### Book 스키마 요약 (Future-ready)
- `id`
- `userId`
- `title`
- `coverImageUri?`
- `normalizedTitle?`
- `createdAt`

### 확장 방향
- AI 자동 Book 그룹핑
- 자동 그룹 추천
- 사용자 수동 재지정 허용

## 개인정보/격리 원칙
- 모든 데이터는 사용자 단위로 완전 격리한다.
- 사용자 간 데이터 노출은 0이어야 한다.
- 사용자 간 crowd 최적화를 하지 않는다.
- 공유 데이터셋을 만들지 않는다.
- 책 매칭 DB를 운영하지 않는다.

## MVP 범위
### 포함
- Capture -> Generate -> GuideDetail
- 세로 스크롤 GuideDetail
- TTS stub
- Save items
- Recent guides list

### 제외
- 점수형 평가 기능
- 공개 공유 기능
- 외부 도서 식별 연동
- 사용자 간 추천 결합

## 톤 & 콘텐츠 철학
- 톤: Calm, Structured, Intelligent, Supportive
- 관점: Parent-coach oriented
- 집중: 엄마의 읽기 이해 지원

### 피해야 할 문체
- 학술적 문장
- 긴 설명
- 반복적 지시 문구
- 과도한 감정 표현
