# Weekly Todo: YYYY-MM-DD ~ YYYY-MM-DD

- Status: Planned / Active / Blocked / Complete / Paused
- Last updated:
- Related Backlog:

1주를 기본 기간으로 사용하되 프로젝트 리듬에 맞게 조정한다. 기간은 계획 단위이고, 실행·검증·기록은 작은 Step 단위다. 작은 작업은 아래 내용을 짧은 항목으로 합치고 해당하지 않는 표는 생략한다.

## Goal and Done Criteria

기간이 끝났을 때 달라져 있어야 하는 소비자 관점의 결과를 적는다. 상세 인수 조건은 해당 Step에 한 번만 기록한다.

- Goal:
- Required Steps / acceptance criteria:
- Out of scope:

## Current State and Inputs

- 확인된 코드·실행 상태와 근거:
- 준비된 명세·계약·데이터·권한:
- 부족한 입력·기존 실패·미결정 사항과 해제 조건:
- 관련 결정·계약·Troubleshooting 링크:

## UI / Consumer Mapping

여러 화면이나 소비자의 관계를 먼저 정리해야 할 때 사용한다. 단일 흐름은 Step의 인수 조건으로 대신한다.

| Consumer / Screen | Action | Data / State / Error | Contract / Source | Status |
|---|---|---|---|---|
|  |  |  |  |  |

## Steps

### Step 1. 제목

- Status: Pending / In Progress / Blocked / Done
- Outcome / scope: 만들 결과, 수정 범위, 계약·데이터 영향, 제외 범위
- Risk / authority: 위험과 이유, 현재 허용된 작업, 중단·복구 조건
- Decisions / assumptions: 기대 결과를 정하는 결정이나 남은 가정의 링크

#### Acceptance

구현 전에 정상 동작과 필요한 실패·경계 사례, 유지할 불변조건을 적는다. 기대 결과는 사용자 요구·확정 정책·공개 계약에서 도출하고 근거를 연결한다. 현재 구현만 보고 정답을 정하지 않는다.

| ID | Consumer scenario / expected result | Basis | Check IDs |
|---|---|---|---|
| A1 |  |  |  |

#### Checks

위험에 필요한 검사를 선택한다. 프로젝트에 이미 있는 명령이나 재현 가능한 수동 절차를 사용하고, 실행 결과는 아래 Verification Log에 기록한다.

| ID | Method / conditions | Required or conditional | Acceptance IDs |
|---|---|---|---|
| C1 |  | Required / 조건과 적용 여부 | A1 |

- 검출력 확인: 버그의 수정 전 실패, 반례, 경계 검사 등 이번 작업에 필요한 방법과 선택 이유
- 검증 기준 변경: 인수 조건·테스트·assertion·skip·mock·제외 설정·CI 변경의 이유와 영향. 변경이 없으면 짧게 표시

#### Result and Next

- Implementation: Not Started / In Progress / Complete
- Verification: Pass / Fail / Blocked / Not Run — 근거가 되는 실행 ID와 남은 한계
- Deployment: Out of Scope / Not Started / Blocked / Deployed — 해당할 때만 대상과 배포 증거
- Next: 남은 일 또는 다음 한 Step

## Verification Log

| Run ID / date | Step / check | Code state | Environment / inputs | Command or procedure | Result | Evidence |
|---|---|---|---|---|---|---|
|  |  |  |  |  | Pass / Fail / Blocked / Not Run |  |

- Code state는 commit과 미커밋·새 파일 변경을 포함한 스냅샷 또는 diff 식별자로 기록한다. 검증을 위해 커밋할 필요는 없다.
- 계획의 명령·조건을 그대로 실행했으면 Checks의 해당 항목을 참조하고, 달랐다면 실제 인자·환경·입력을 기록한다. 원본 로그나 화면은 복제하지 않고 링크한다.
- 코드·테스트·설정이 바뀌면 영향을 받는 검사를 다시 실행한다. 최종 변경의 완료를 판단할 때 기존 증거를 재사용하려면 그 검사의 대상과 전제가 바뀌지 않았음을 확인한다. 무관한 문서 변경만으로 전체 검사를 반복하지 않는다.
- 실행할 수 없었던 검사도 사유와 해제 조건을 남긴다. 기존 실패와 이번 변경의 실패를 구분한다.

## Period Result and Handoff

- Achieved: 검증된 결과와 Step 링크
- Remaining: 구현되었지만 미검증인 것, 차단 요소, 알려진 한계
- Decisions / troubleshooting: 새로 생기거나 바뀐 사실의 책임 문서 링크
- Next: 다음 세션이 시작할 가장 작은 한 Step

## Update and Completion Rules

- Step 시작 전에 범위·인수 조건·필수 검사·허용 범위를 정한다. 기존 권한 안의 구현과 수리는 다시 승인받지 않고 진행한다.
- 같은 실패가 반복되는데 새 근거가 없거나, 권한·범위·위험 경계를 넘게 되면 그 작업을 멈추고 원인과 필요한 결정을 기록한다. 독립적으로 진행 가능한 안전한 작업은 계속할 수 있다.
- 정당한 요구 변경은 근거와 영향을 기록해 인수 조건과 검사를 함께 갱신한다. 통과를 얻기 위해 몰래 기준을 낮추지 않는다.
- `Done`은 인수 조건을 충족하고 최종 코드 상태의 모든 필수 검사가 `Pass`이며 증거가 있을 때만 사용한다. 필수 검사의 `Fail`, `Blocked`, `Not Run`은 `Done`이 아니다.
- 구현 완료와 검증 완료, 배포 상태를 구분한다. 배포가 범위 밖이면 Step 완료에 배포를 요구하지 않으며, 범위 안이면 관련 인수 조건과 검증을 포함한다.
- 각 Step의 결과와 다음 시작점을 즉시 갱신한다. 다른 책임 문서는 해당 사실이 바뀐 경우에만 갱신하고 여기서는 링크한다.
