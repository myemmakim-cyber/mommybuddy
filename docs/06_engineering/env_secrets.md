# 환경변수/시크릿 템플릿

## 원칙
- 시크릿은 코드/문서에 평문 저장하지 않는다.
- 환경별(dev/stage/prod) 분리 관리한다.

## 환경변수 목록
| 키 | 설명 | 필수 | 예시 값 |
|---|---|---|---|
| `APP_ENV` | 실행 환경 | Y | `dev` |
| `API_BASE_URL` | API 엔드포인트 | Y | `TODO` |
| `AUTH_SECRET` | 인증 시크릿 | Y | `TODO` |
| `TTS_API_KEY` | TTS 연동 키 | Y | `TODO` |
| `ANALYTICS_KEY` | 분석 키 | N | `TODO` |

## 주입 방식
- 로컬: (TODO)
- CI: (TODO)
- 운영: (TODO)

## 보안 체크리스트
- [ ] `.env` 파일 git 추적 제외
- [ ] 키 롤링 주기 정의
- [ ] 최소 권한 원칙 적용
- [ ] 유출 대응 프로세스 문서화
