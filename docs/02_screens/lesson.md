# 학습 가이드 상세 화면 명세 (GuideDetail)

## 화면 목적
- 한 페이지에서 생성된 Guide를 세로 스크롤로 끝까지 읽게 한다.
- 엄마가 아이와 바로 대화/읽기 확장을 실행하도록 돕는다.

## 화면 고정 구조 (표시 순서 엄수)
1. Header (Back + "학습 가이드")
2. Book Info
3. Scene Insight
4. Book Sentences
5. Key Words
6. CROW Questions
7. Supporting Phrases
8. Parent Tips

## 섹션별 목적
### 1) Header
- 뒤로가기, 저장 토글, 화면 제목 제공

### 2) Book Info
- 책 제목(있으면), 페이지 인덱스(있으면), 생성 시각 표시

### 3) Scene Insight
- 장면 핵심을 2~4문장으로 짧게 요약

### 4) Book Sentences
- 책 속 핵심 문장 제시

### 5) Key Words
- 장면 이해에 중요한 단어/의미 제시

### 6) CROW Questions (중앙 섹션)
- C/R/O/W/D 타입별 질문과 후속 질문 제공
- 부모-아이 대화 확장을 최우선 목표로 둔다.

### 7) Supporting Phrases
- 엄마가 바로 따라 말할 수 있는 보조 문장 제공

### 8) Parent Tips
- 읽기 진행 전략을 짧은 실행 문장으로 제공

## 영어 문장 표시 규칙 (필수)
- 모든 영어 항목은 아래 3줄 형식으로 노출한다.

```text
English sentence
▶ (audio button)
Korean meaning below (muted text)
```

- 적용 대상:
- Book Sentences
- Key Words
- CROW Questions
- Follow-up Questions
- Supporting Phrases

- 금지:
- 발음기호
- 한글 발음 표기

## 인터랙션
- 세로 스크롤로 전체 섹션 탐색
- 각 영어 문장의 오디오 버튼 탭(재생/중지, stub 허용)
- 저장 토글
- CROW 질문 복사(선택)

## 데이터 바인딩
| UI 요소 | 데이터 키 | 타입 | 규칙 |
|---|---|---|---|
| 가이드 ID | `guide.id` | string | 필수 |
| 책 ID | `guide.bookId` | string/null | MVP nullable |
| 페이지 인덱스 | `guide.pageIndex` | number/null | MVP nullable |
| 이미지 URI | `guide.imageUri` | string | 필수 |
| 장면 핵심 | `guide.content.sceneInsight` | string | 필수 |
| 책 속 문장 | `guide.content.bookSentences[]` | array | 최소 1개 |
| 핵심 단어 | `guide.content.keyWords[]` | array | 0개 허용 |
| CROW 질문 | `guide.content.crowdQuestions[]` | array | 타입 C/R/O/W/D |
| 보조 문장 | `guide.content.extraPhrases[]` | array | 0개 허용 |
| 엄마표 Tip | `guide.content.parentStrategies[]` | array | 최소 1개 권장 |

## 이벤트
- `screen_guide_detail_view`
- `guide_section_impression`
- `cta_guide_audio_click`
- `cta_guide_save_click`
- `cta_guide_back_click`

## 예외/오류 처리
- 가이드 조회 실패: 재시도 + 홈 이동 버튼
- TTS URL 없음: stub 재생 처리 또는 비활성 안내
- 일부 섹션 비어있음: 섹션은 유지하고 "준비 중" 문구 표기

## QA 체크리스트
- [ ] 섹션 순서 고정 렌더링 검증
- [ ] 영어 문장 3줄 표시 규칙 100% 적용
- [ ] 숨김 섹션/아코디언 미사용 검증
- [ ] 저장 상태 즉시 반영 검증
