# 코드 발췌

팀 저장소에서 제가 작성한 파일 일부를 그대로 옮겼습니다. 주석의 내부 문서 참조만 지웠습니다.

| 파일 | 내용 |
|---|---|
| `api-server/AnalysisStage.java` | 일별 분석 단계 순서 |
| `api-server/AnalysisRunner.java` | 분석 실행기. 실행 소유권(advisory lock), 단계별 실행, 실패 기록, 재시도 간격, 완료 공개 |
| `worker/analysis_entry.py` | Spring이 단계마다 호출하는 워커 진입점. 단계와 모듈 연결, 종료 코드 규약 |
| `worker/report_matching.py` | 송신 은행과 수신 은행 보고의 일대일 매칭, 식별 정보 충돌과 결측 판정 |
| `worker/seed_promotion.py` | 모델이 놓친 거래를 의심 씨앗과의 계좌 공유, 금액 비율 연쇄로 보완 |
| `worker/alert_scope.py` | 한 번의 Alert 구성이 읽는 범위 결정 |
| `worker/run_fence.py` | 단계 실행 전 소유권 확인과 체크포인트 저장 |
| `worker/score_contract.py` | 모델과 무관한 점수 결과 검사 |
| `worker/tests/` | 위 매칭과 씨앗 보완의 단위 테스트 |
| `inference-server/replica.py` | 추론 서버의 원장 사본. 전체 교체와 변경분 반영, 불일치 감지 |

일부 파일만 옮겼기 때문에 import 대상이 없는 모듈이 있고, 이 폴더만으로는 실행되지 않습니다.
