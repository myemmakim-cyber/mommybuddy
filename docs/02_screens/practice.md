# 캡처 화면 명세 (Capture)

## 화면 목적
- 단일 페이지 이미지를 확보해 Guide 생성 입력으로 전달한다.

## 주요 구성요소
- 카메라 촬영
- 앨범 업로드
- 이미지 미리보기
- 재촬영/교체
- `가이드 생성` CTA

## 상태
- 기본
- 카메라 권한 요청
- 미리보기 확인
- 업로드 중
- 오류

## 인터랙션
- 촬영 또는 업로드
- 이미지 확인 후 재선택
- `가이드 생성` 탭 -> Generate 이동

## 데이터 바인딩
| UI 요소 | 데이터 키 | 타입 | 규칙 |
|---|---|---|---|
| 이미지 URI | `capture.imageUri` | string | 필수 |
| OCR 텍스트(선택) | `capture.ocrText` | string | nullable |
| 요청 시각 | `capture.requestedAt` | datetime | 선택 |

## 이벤트
- `screen_capture_view`
- `capture_photo_taken`
- `capture_upload_selected`
- `capture_photo_retake`
- `cta_capture_generate_click`

## MVP vs Later
### MVP
- 촬영/업로드
- 미리보기
- 생성 진입

### Later
- 이미지 품질 자동 보정
- 페이지 경계 자동 감지

## QA 체크리스트
- [ ] 권한 거부 시 업로드 대체 경로 제공
- [ ] 생성 버튼 중복 탭 방지
- [ ] 저품질 이미지 경고 노출
