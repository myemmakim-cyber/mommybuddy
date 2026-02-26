# 페이지 캡처 화면 명세 (Capture)

## 화면 목적
- 책의 단일 페이지 이미지를 빠르게 확보한다.
- Guide 생성을 위한 입력 품질을 보장한다.

## 주요 구성요소
- 카메라 프리뷰/이미지 업로드
- 촬영 버튼
- 재촬영 버튼
- 다음 단계 CTA: `가이드 생성`
- 안내 카피: 흔들림/빛반사 최소화

## 상태
- 기본(카메라 준비)
- 권한 요청 필요
- 미리보기 확인
- 업로드 중
- 오류

## 인터랙션
- 촬영 또는 앨범 업로드
- 이미지 확인 후 재촬영
- `가이드 생성` 탭 -> 생성 화면 이동

## 데이터 바인딩
| UI 요소 | 데이터 키 | 타입 | 규칙 |
|---|---|---|---|
| 임시 이미지 URI | `capture.imageUri` | string | 필수 |
| OCR 후보 텍스트 | `capture.ocrText` | string | 선택 |
| 생성 요청 시각 | `capture.requestedAt` | datetime | 선택 |

## 이벤트
- `screen_capture_view`
- `capture_photo_taken`
- `capture_photo_retake`
- `cta_capture_generate_click`

## QA 체크리스트
- [ ] 권한 거부 시 대체 경로(업로드) 제공
- [ ] 저해상도 이미지 경고 노출
- [ ] 생성 버튼 중복 탭 방지
