# 마이페이지 화면 명세 (MyPage)

## 화면 목적
- 엄마의 독서 지도 성장 기록을 확인한다.
- 읽기 계획과 계정/환경 설정을 관리한다.

## 핵심 UX
- 성장을 점수 경쟁이 아닌 실천 기록 관점으로 보여준다.
- 문구 톤은 차분하고 코칭 중심으로 유지한다.

## 주요 구성요소
- 프로필 요약
- 성장 기록 요약(생성 Guide 수, 최근 읽기 일자, 자주 쓴 질문 타입)
- 읽기 계획(주간 목표/리마인드)
- 설정(언어, 오디오, 개인정보)
- 로그아웃

## 상태
- 기본
- 로딩
- 저장 중
- 오류

## 인터랙션
- 주간 계획 수정
- 언어 변경
- 오디오 설정 변경
- 개인정보/데이터 관리 진입
- 로그아웃

## 데이터 바인딩
| UI 요소 | 데이터 키 | 타입 | 규칙 |
|---|---|---|---|
| 사용자 이름 | `mypage.user.name` | string | 필수 |
| 총 Guide 수 | `mypage.growth.totalGuides` | number | 0 이상 |
| 최근 읽기 일자 | `mypage.growth.lastReadAt` | datetime/null | nullable |
| 질문 타입 분포 | `mypage.growth.crowUsage` | object | C/R/O/W/D |
| 주간 목표 | `mypage.plan.weeklyTarget` | number | TODO 기준 |
| 언어 | `mypage.settings.locale` | string | ko/en |
| 오디오 사용 | `mypage.settings.audioEnabled` | boolean | 기본 정책 TODO |

## 이벤트
- `screen_mypage_view`
- `cta_mypage_plan_edit_click`
- `cta_mypage_locale_change`
- `cta_mypage_audio_toggle_click`
- `cta_mypage_privacy_click`
- `cta_mypage_logout_click`

## MVP vs Later
### MVP
- 성장 기록 기본 요약
- 주간 계획 입력
- 설정 관리

### Later
- 코칭 리포트 자동 요약
- 성장 패턴 기반 개인 제안

## QA 체크리스트
- [ ] 성장 기록 수치 정확성 검증
- [ ] 설정 변경 영속화 검증
- [ ] 개인정보 관리 경로 접근 검증
