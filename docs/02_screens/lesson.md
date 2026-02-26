# 레슨 화면 템플릿

## 화면 목적
- 핵심 학습 카드 2장을 직관적으로 소화하게 한다.
- 스와이프 상호작용으로 집중도를 높인다.

## 주요 구성요소
- 상단: 레슨 제목, 진행도, 닫기/뒤로
- 본문: 카드 덱(2장 겹침), 카드 콘텐츠(문장/설명/예문)
- 하단: 이전/다음 보조 버튼, TTS 재생, 저장 버튼

## 상태
- `idle`: 첫 진입 상태
- `card_front`: 상단 카드 활성
- `card_back`: 하단 카드 대기
- `swiping`: 드래그 중
- `swipe_completed`: 카드 전환 완료
- `loading`: 데이터 로딩
- `error`: 데이터/재생 오류

## 인터랙션 (카드 2장 겹침 스와이프)
- 기본 배치:
- 전면 카드 1장 + 후면 카드 1장을 겹쳐 표시
- 후면 카드는 스케일 축소/오프셋 적용
- 스와이프 규칙:
1. 사용자가 전면 카드를 좌/우로 드래그한다.
2. 임계값 `(TODO: px 또는 비율)` 초과 시 전면 카드를 화면 밖으로 이탈시킨다.
3. 후면 카드가 전면으로 승격된다.
4. 다음 카드가 있으면 새 후면 카드를 추가한다.
5. 마지막 카드 완료 시 연습 화면으로 이동 CTA 노출.
- 보조 조작:
- 버튼 탭으로도 이전/다음 이동 가능
- 스와이프 취소 시 원위치 스냅 애니메이션

## 데이터 바인딩
| UI 요소 | 데이터 키 | 타입 | 규칙 |
|---|---|---|---|
| 레슨 제목 | `lesson.title` | string | 필수 |
| 카드 목록 | `lesson.cards[]` | array | 최소 2장 |
| 카드 본문 | `lesson.cards[i].text` | string | 필수 |
| 카드 설명 | `lesson.cards[i].hint` | string | 선택 |
| 오디오 URL | `lesson.cards[i].ttsUrl` | string | 없으면 생성 요청 |
| 저장 여부 | `saved.isSaved` | boolean | 토글 가능 |

## 이벤트
- 화면 진입: `screen_lesson_view`
- 카드 노출: `lesson_card_impression`
- 스와이프 완료: `lesson_card_swipe_completed`
- 보조 버튼 클릭: `cta_lesson_next_click`, `cta_lesson_prev_click`
- 저장 토글: `cta_lesson_save_click`
- TTS 재생: `cta_lesson_tts_play_click`
- 레슨 완료: `lesson_completed`

## 예외/오류 처리
- 카드 데이터 2장 미만: 대체 UI + 신고 버튼
- TTS 실패: 재시도 버튼 + 텍스트 안내
- 네트워크 실패: 재시도/나가기 선택

## QA 체크리스트
- [ ] 스와이프 임계값 동작 검증
- [ ] 스와이프 중 프레임 드랍 기준 `(TODO)`
- [ ] 저장 상태 즉시 반영
- [ ] 마지막 카드 완료 후 다음 단계 진입
