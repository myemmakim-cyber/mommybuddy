# 데이터 모델 템플릿

## 목적
- 핵심 엔터티(User, Lesson, Progress, Saved, TTSJob)를 정의한다.

## 엔터티 정의
### User
| 필드 | 타입 | 필수 | 설명 |
|---|---|---|---|
| `id` | string | Y | 사용자 ID |
| `name` | string | Y | 표시 이름 |
| `locale` | string | Y | `ko`/`en` |
| `createdAt` | datetime | Y | 생성 시각 |

### Lesson
| 필드 | 타입 | 필수 | 설명 |
|---|---|---|---|
| `id` | string | Y | 레슨 ID |
| `title` | string | Y | 제목 |
| `difficulty` | string | Y | 난이도 |
| `cards` | array | Y | 카드 목록(최소 2) |
| `updatedAt` | datetime | Y | 수정 시각 |

### Progress
| 필드 | 타입 | 필수 | 설명 |
|---|---|---|---|
| `id` | string | Y | 진행 ID |
| `userId` | string | Y | 사용자 참조 |
| `lessonId` | string | Y | 레슨 참조 |
| `status` | string | Y | `in_progress/completed` |
| `score` | number | N | 퀴즈 점수 |
| `completedAt` | datetime | N | 완료 시각 |

### Saved
| 필드 | 타입 | 필수 | 설명 |
|---|---|---|---|
| `id` | string | Y | 저장 ID |
| `userId` | string | Y | 사용자 참조 |
| `lessonId` | string | Y | 레슨 참조 |
| `savedAt` | datetime | Y | 저장 시각 |

### TTSJob
| 필드 | 타입 | 필수 | 설명 |
|---|---|---|---|
| `id` | string | Y | 작업 ID |
| `lessonId` | string | Y | 레슨 참조 |
| `cardId` | string | Y | 카드 참조 |
| `status` | string | Y | `queued/processing/done/failed` |
| `audioUrl` | string | N | 결과 URL |
| `errorCode` | string | N | 실패 코드 |

## 관계
- User 1:N Progress
- User 1:N Saved
- Lesson 1:N Progress
- Lesson 1:N TTSJob

## 오픈 이슈
- [ ] 보관 기간(retention) 정책
- [ ] 삭제/비식별화 정책
