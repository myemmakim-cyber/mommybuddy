# GuideDetail 화면 명세 (파일 유지: lesson.md)

## 화면 목적
- 한 페이지에서 생성된 Guide를 세로 스크롤로 끝까지 소비하게 한다.
- 엄마가 아이와 읽기 대화를 즉시 실행하도록 돕는다.

## 화면 구조 (고정 순서)
1. Book Info (title/date/child age/mom level)
2. Reading Tips
3. Book Sentences
4. Key Words (word only)
5. Extra Phrases
6. CROW-based Questions (Completion/Recall/Open-ended/Wh/Distancing + follow-ups)
7. Parent Strategies

## 섹션 정의
### 1) Book Info
- 노출 항목: 책 제목, 생성일, 아이 연령, 엄마 레벨
- 목적: 현재 읽기 맥락을 빠르게 정렬

### 2) Reading Tips
- 짧고 실전형 읽기 팁 2~4개
- 목적: 읽기 진행 전에 엄마의 말투/속도/질문 타이밍 정렬

### 3) Book Sentences
- 페이지 핵심 문장 목록
- 목적: 본문 중심 읽기 기반 확보

### 4) Key Words (word only)
- 단어 중심 노출 (문장형 설명 최소화)
- 목적: 장면 이해 핵심 어휘 확보

### 5) Extra Phrases
- 엄마가 자연스럽게 덧붙일 수 있는 짧은 문장
- 목적: 읽기 확장 대화 유도

### 6) CROW-based Questions
- 타입: Completion / Recall / Open-ended / Wh / Distancing
- 각 메인 질문에 후속 질문 2~4개 포함
- 목적: 아이의 이해 확장과 사고 연결

### 7) Parent Strategies
- 짧은 코칭 팁 목록
- 목적: 엄마의 독서 지도 역량 성장 지원

## CRITICAL DISPLAY RULE (MUST)
- 학습 UI의 모든 영어 문자열은 아래 포맷으로 렌더링한다.

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
- 발음 텍스트

## 스크롤/레이아웃 규칙
- 전체 콘텐츠는 단일 세로 스크롤로 제공한다.
- 섹션 순서는 고정한다.
- 콘텐츠 숨김/접기 UI를 사용하지 않는다.

## 인터랙션
- 영어 라인별 오디오 재생 버튼 탭
- 저장 토글
- 뒤로가기

## 데이터 바인딩
| UI 요소 | 데이터 키 | 타입 | 규칙 |
|---|---|---|---|
| 가이드 ID | `guide.id` | string | 필수 |
| 책 제목 | `guide.bookTitle` | string/null | nullable |
| 생성일 | `guide.createdAt` | datetime | 필수 |
| 아이 연령 | `guide.childAge` | string/null | nullable |
| 엄마 레벨 | `guide.momLevel` | string/null | nullable |
| Reading Tips | `guide.content.readingTips[]` | array | 2~4개 권장 |
| 문장 목록 | `guide.content.bookSentences[]` | array | 영어/한국어 쌍 |
| 단어 목록 | `guide.content.keyWords[]` | array | word 중심 |
| 보조 문장 | `guide.content.extraPhrases[]` | array | 영어/한국어 쌍 |
| CROW 질문 | `guide.content.crowdQuestions[]` | array | 타입 C/R/O/W/D |
| 후속 질문 | `guide.content.crowdQuestions[i].followUps[]` | array | 2~4개 권장 |
| 부모 전략 | `guide.content.parentStrategies[]` | array | 짧은 문장 |

## 이벤트
- `screen_guide_detail_view`
- `guide_section_impression`
- `cta_guide_audio_click`
- `cta_guide_save_click`
- `cta_guide_back_click`

## MVP vs Later
### MVP
- 고정 섹션 순서
- 영어 + 오디오 + 한국어 표시 규칙
- 저장 기능

### Later
- 섹션별 개인 선호 반영
- 오디오 품질 고도화

## 예외/오류 처리
- 조회 실패: 재시도 + 홈 이동
- 오디오 URL 없음: stub 재생 또는 비활성 안내
- 일부 데이터 비어있음: 섹션 유지 + 대체 문구 표시

## QA 체크리스트
- [ ] 섹션 순서 일치 검증
- [ ] 영어 문자열 표시 규칙 100% 준수
- [ ] 후속 질문 개수(2~4) 정책 검증
- [ ] 숨김/접기 UI 미사용 검증
