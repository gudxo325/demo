# 논문 추천 — 2026-08-20

## 검색 정보

- **연구 기준일**: 2026-08-20 (`REQUESTED_DATE` 미지정, Asia/Seoul 기준 전날 사용)
- **실제 검색 창**: 1일(2026-08-20~2026-08-20) → 결과 없음 → 7일(2026-08-14~2026-08-20) → 결과 없음 → 30일(2026-07-21~2026-08-20) → 11건 검색됨
- **검색 쿼리**: `chest X-ray deep learning diagnosis`

## 코호트 개요 (집계 수준)

- 총 272건의 흉부 X-ray 영상 레코드, 고유 환자 153명
- 성별: 남 136 / 여 136, 평균 연령 남 48.7세 / 여 54.3세 (전체 범위 9~87세, 평균 51.5세)
- 촬영 방향: PA 184건, AP 88건
- 기관 분포: INST01 62건, INST02 56건, INST03 54건, INST05 52건, INST04 48건 (5개 기관)
- 장비 분포: DEV01~DEV09, 9개 장비 (최소 15건 ~ 최대 40건)
- 소견 라벨: No Finding 145건, Infiltration 21건, Atelectasis 16건, Nodule 7건, Fibrosis 6건, Effusion 6건, Cardiomegaly 5건, Pneumothorax 5건 등 다수 병변 조합 존재
- 데이터는 전량 합성(is_synthetic=true) 표시

## 선정 논문

### 1. CLEAR: an auditable foundation model for radiology grounded in clinical concepts
*Nature Biomedical Engineering, 2026-07-22 (OpenAlex)*
https://doi.org/10.1038/s41551-026-01741-4

미국·유럽·아시아 4개 외부 데이터셋에서 검증된 개념 기반 흉부 X-ray 파운데이션 모델. 우리 코호트가 5개 기관·9개 장비에 걸친 다기관·다병변 소규모 데이터라는 점에서, 이 논문이 강조하는 기관 간 일반화와 예측 근거 설명 가능성이 실무 적용 시 참고할 만합니다. 다만 검증 규모(수십만 명)와 우리 코호트(153명) 사이 격차가 커 동일한 성능 재현 여부는 확인할 수 없습니다.

### 2. Grounding Radiology Report Findings into Medical Image Segmentation (CF2Seg)
*npj Digital Medicine, 2026-07-28 (OpenAlex)*
https://doi.org/10.1038/s41746-026-03051-0

리포트 텍스트만으로 병변 위치를 학습하는 분할 프레임워크. 우리 데이터에는 findings_label과 report_text가 함께 있고 조합 라벨(Effusion|Infiltration 등)이 다수 존재해, 픽셀 단위 주석 없이 다기관 아카이브를 재활용하는 이 접근이 유용할 수 있습니다. 단, 우리 데이터에는 검증용 전문가 분할 마스크가 없어 실제 정확도는 확인 불가합니다.

### 3. UniMedDiff: a knowledge-enhanced diffusion model for medical image generation from clinical reports
*npj Digital Medicine, 2026-08-13 (OpenAlex)*
https://doi.org/10.1038/s41746-026-03135-x

리포트 기반 확산 모델로 실제 데이터 1%만 추가해도 전체 데이터에 근접한 분류 성능을 달성. 우리 코호트는 No Finding이 절반 이상을 차지하고 Pneumothorax·Fibrosis 등 희귀 병변은 3~7건에 불과한 뚜렷한 불균형이 있어, 합성 증강이 희귀 소견 학습에 실질적 도움이 될 가능성이 있습니다. 다만 합성 영상의 임상적 신뢰도는 이 논문만으로 보장되지 않습니다.

## 공통 비교 축 (axes)

- **기관 간 일반화**: 다기관 데이터에서의 모델 성능 안정성
- **리포트-영상 연계**: 텍스트 리포트를 영상 분석(위치추정, 생성)에 활용하는 방법
- **라벨 불균형 대응**: 희귀 소견 클래스에 대한 데이터/학습 전략

## 검토 안내

본 추천은 자동 검색·선별 결과이며, 실제 임상 적용 여부는 반드시 담당 의료진의 검토를 거쳐야 합니다.
