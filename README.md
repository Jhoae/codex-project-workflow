# Codex Project Workflow

특정 기술이나 저장소 구조에 종속되지 않는 프로젝트 실행 지침과 문서 템플릿 모음이다. Codex가 프로젝트를 시작할 때 사실을 확인하고, UI 또는 소비자 관점에서 요구사항을 역산하고, 전체 Backlog와 주 단위 Todo를 연결하고, 작업을 작은 Step으로 나누어 구현·검증·기록하도록 돕는다.

이 저장소의 목표는 많은 문서를 만드는 것이 아니다. **현재 상태, 결정, 실행 범위, 문제 해결 지식을 서로 다른 책임으로 관리해 다음 작업이 추측이 아니라 증거에서 시작되게 하는 것**이다.

## 핵심 작업 방식

1. 구현 전에 사실과 성공 조건을 확인한다.
2. UI가 있으면 화면과 사용자 행동에서, UI가 없으면 실제 소비자에서 요구사항을 역산한다.
3. 전체 할 일은 Backlog에, 이번 주에 끝낼 일은 Weekly Todo에 둔다.
4. 현재 할 일을 독립적으로 검증 가능한 작은 Step으로 나눈다.
5. 각 Step을 구현하고 검증한 직후 같은 Todo를 갱신한다.
6. 결정은 Decision Log에, 되돌리기 어려운 기술 선택은 별도 기술 결정 문서에 남긴다.
7. 중요한 문제 해결 과정은 Troubleshooting Log로 분리해 재사용 가능한 지식으로 만든다.
8. 작업을 넘기거나 중단하기 전에 Context / Handoff에 현재 상태와 다음 한 Step을 남긴다.

## 파일 구성

| File | Purpose |
|---|---|
| [`AGENTS.md`](AGENTS.md) | Codex가 반복 적용할 계획·구현·검증·기록 원칙 |
| [`templates/PROJECT_CONTEXT.md`](templates/PROJECT_CONTEXT.md) | 현재 상태, 제약, 위험, 다음 시작점을 전달하는 context / handoff |
| [`templates/BACKLOG.md`](templates/BACKLOG.md) | 전체 목표와 `Now`, `Next`, `Later`, `Out of Scope` 관리 |
| [`templates/WEEKLY_TODO.md`](templates/WEEKLY_TODO.md) | 한 주의 목표, 작은 Step, 진행 기록, 검증 결과 관리 |
| [`templates/DECISION_LOG.md`](templates/DECISION_LOG.md) | 확정·제안·대체된 결정을 시간순으로 기록 |
| [`templates/TECHNOLOGY_DECISION.md`](templates/TECHNOLOGY_DECISION.md) | 되돌리기 어려운 기술·구조 결정의 근거와 영향 기록 |
| [`templates/TROUBLESHOOTING.md`](templates/TROUBLESHOOTING.md) | 증상, 증거, 원인, 해결, 검증, 한계를 분리해 기록 |

## 프로젝트에 적용하기

### 1. 지침 배치

`AGENTS.md`를 대상 저장소의 루트에 복사한다. 이미 `AGENTS.md`가 있다면 파일을 덮어쓰지 말고, 이 저장소의 범용 원칙과 기존 프로젝트 규칙을 합친다. 프로젝트별 명령, 구조, 품질 기준처럼 더 구체적인 규칙은 범용 원칙보다 우선하도록 명시한다.

Codex는 작업 전에 `AGENTS.md`를 읽고, 저장소 루트에서 현재 작업 디렉터리까지 발견한 지침을 순서대로 결합한다. 더 가까운 디렉터리의 지침으로 특정 영역의 규칙을 구체화할 수 있다. 자세한 동작은 [Codex의 `AGENTS.md` 공식 문서](https://developers.openai.com/codex/guides/agents-md)를 참고한다.

### 2. 필요한 템플릿만 복사

프로젝트에 기존 문서 체계가 없다면 다음 구조로 시작할 수 있다.

```text
AGENTS.md
docs/project-context.md
docs/backlog.md
docs/todo/YYMMDD~YYMMDD.md
docs/decisions.md
docs/technology-decisions/
docs/troubleshooting.md
docs/archive/
```

모든 템플릿을 의무적으로 만들 필요는 없다.

- 작은 단일 작업: `AGENTS.md`와 현재 Todo만 사용한다.
- 여러 주에 걸친 기능: Context, Backlog, Weekly Todo를 사용한다.
- 계약·데이터·운영 영향이 큰 작업: Decision Log와 Technology Decision을 추가한다.
- 재현과 원인 분석이 필요한 문제: Troubleshooting Log를 추가한다.

기존 이슈 트래커나 문서 체계가 있으면 새 체계를 중복 생성하지 말고, 각 템플릿의 책임을 기존 위치에 대응시킨다.

### 3. 첫 작업 요청

다음과 같이 시작할 수 있다.

```text
AGENTS.md와 현재 프로젝트 문서를 먼저 읽어줘.
현재 상태, 목표, 제약, 미확정 사항을 구분하고,
Backlog와 이번 주 Todo를 정렬한 뒤 첫 번째 검증 가능한 Step만 제안해줘.
UI가 있는 작업은 화면과 사용자 행동에서 필요한 데이터와 계약을 역산해줘.
각 Step 완료 직후 Todo와 관련 기록을 갱신해줘.
```

처음부터 구현을 원하면 마지막 문장을 다음처럼 바꾼다.

```text
계획을 확인한 뒤 안전한 범위에서 구현과 검증까지 진행하고,
각 Step 결과를 문서에 즉시 반영해줘.
```

### 4. 주간 운영

주 초에는 Backlog의 `Now`에서 이번 주 Done Criteria를 만족할 범위만 Weekly Todo로 가져온다. 작업 중에는 한 Step을 시작할 때 `In Progress`, 검증이 끝났을 때만 `Done`으로 바꾼다. 주가 끝나면 결과와 미완료 사유를 남기고 문서를 보존한 뒤, 다음 주에는 새 Todo를 만든다.

Backlog에는 장기 우선순위만 유지하고 세부 실행 로그를 누적하지 않는다. Weekly Todo에는 현재 실행 상태를 유지하되, 긴 결정 근거나 문제 분석은 전용 문서로 옮기고 링크한다.

## 적용 원칙

- 이 문서보다 최신 사용자 결정과 프로젝트별 지침이 우선한다.
- 문서는 사실의 주 저장 위치를 하나만 두고 서로 링크한다.
- 단순한 작업에는 필요한 규칙만 적용하고, 위험과 복잡도가 커질수록 기록과 검증을 강화한다.
- 실제로 실행하지 않은 검증을 완료했다고 표시하지 않는다.
- 절대 경로, 개인 계정, 비밀값, 특정 환경의 식별 정보를 범용 문서에 넣지 않는다.
- 완료 시점에는 결과, 검증, 한계, 다음 Step이 서로 구분되어 있어야 한다.

## License

MIT License. 자세한 내용은 [`LICENSE`](LICENSE)를 참고한다.
