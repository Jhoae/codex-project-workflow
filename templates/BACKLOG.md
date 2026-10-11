# Project Backlog

- Last updated:
- Scope:

상세 실행 로그가 아니라 프로젝트 전체 결과, 우선순위, 의존성, 완료 조건을 관리한다.

## Now

| ID | Outcome | Purpose | Done Criteria | Dependencies | Status | Current Todo |
|---|---|---|---|---|---|---|
|  |  |  |  |  | Proposed / Ready / In Progress / Blocked / Done |  |

## Next

| ID | Outcome | Purpose | Done Criteria | Dependencies | Status |
|---|---|---|---|---|---|
|  |  |  |  |  | Proposed / Ready / Blocked |

## Later

| ID | Outcome | Why Later | Revisit Condition | Dependencies |
|---|---|---|---|---|
|  |  |  |  |  |

## Out of Scope

| Item | Reason | Revisit Condition |
|---|---|---|
|  |  |  |

## Replaced or Cancelled

| Item | Status | Reason | Replaced By | Related Decision |
|---|---|---|---|---|
|  | Superseded / Cancelled |  |  |  |

## Maintenance Rules

- 현재 우선순위와 완료 조건이 바뀌면 즉시 갱신한다.
- 한 주의 세부 작업과 실패 로그는 Backlog에 누적하지 않는다.
- 중요한 사용자 결과를 검증할 수 없는 공백은 검사·환경 개선 작업으로 남기고, 확인할 결과와 완료 조건을 연결한다.
- 항목을 없애기보다 보류, 취소, 대체 이유를 남긴다.
- `Done`은 연결된 인수 조건을 충족하고 해당 코드 상태의 필수 검사가 모두 통과한 증거가 있을 때만 사용한다. 구현만 끝났거나 필수 검사가 `Blocked` / `Not Run`이면 완료가 아니다.
