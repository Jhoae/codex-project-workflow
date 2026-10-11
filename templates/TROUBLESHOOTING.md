# Troubleshooting Log

- Last updated:
- Scope:

반복할 가능성이 있거나 영향이 큰 문제를 기록한다. 짧은 일회성 실패는 Todo의 결과로 충분하며, 같은 실행 로그를 두 곳에 복제하지 않는다.

## YYYY-MM-DD - 문제 제목

### Status

Investigating / Mitigated / Resolved / Unresolved

### Symptom and Impact

관찰된 현상과 사용자·데이터·운영에 미친 영향을 적는다. 증상과 원인 추정을 섞지 않는다.

### Reproduction and Baseline

입력·환경·코드 상태·재현 절차와 변경 전 결과를 연결한다. 비밀값과 개인 정보는 제거한다. 재현할 수 없으면 이유와 남은 불확실성을 적는다.

### Hypotheses and Evidence

| Hypothesis | Supporting / contradicting evidence | Check | Result / run link |
|---|---|---|---|
|  |  |  |  |

### Cause

확인된 원인을 적는다. 아직 확인되지 않았다면 `Unknown`으로 둔다.

### Resolution and Limits

- 선택한 조치와 이유, 주요 대안:
- 수정 범위와 계약·데이터 영향:
- 임시 우회인지 근본 해결인지, 남은 한계:
- 현재 허용 범위, 중단·복구 조건:

### Verification and Regression

| Expected behavior / basis | Before / after runs | Regression check | Remaining gap |
|---|---|---|---|
|  |  |  |  |

- Before / after runs는 코드 상태·환경·실제 명령·결과·증거가 담긴 Todo 실행 기록이나 동등한 원본 기록에 연결한다.
- 가능하면 동일한 회귀 검사가 수정 전에는 해당 버그 때문에 실패하고 수정 후에는 통과하는지 확인한다. 실행하지 않은 결과는 `Not Run`, 환경 등으로 막힌 결과는 `Blocked`로 남긴다.
- Regression check에는 재발을 잡을 테스트·입력 fixture·계약 검사·운영 점검의 실제 위치와 실행 방법을 연결한다. 자동화가 적절하지 않으면 반복 가능한 수동 확인과 한계를 적는다.
- 테스트나 판정 기준을 변경했다면 그 근거와 검출력에 미치는 영향을 남긴다. 증상을 숨기거나 검사를 약화해 얻은 통과를 해결 증거로 삼지 않는다.

### Result and Follow-up

- 검증된 해결 범위:
- 구현되었지만 미검증인 부분, 재발 조건:
- 남은 검사·결정과 다음 Step:

해당 문제의 해결 조건과 필수 검증을 충족했을 때만 `Resolved`로 표시한다. 임시 완화나 검증 차단을 해결 완료로 표시하지 않는다.
