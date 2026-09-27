# PL-7008 한국어 실습 번역 및 유지관리 지침

## 1. 목적

이 디렉터리는 `../Labs`에 있는 PL-7008 영문 실습의 한국어 번역본을 관리합니다.

- 영문 원본은 수정하지 않습니다.
- 한국어 파일은 영문 원본과 동일한 파일명과 문서 구조를 유지합니다.
- 자연스러운 한국어를 사용하되, 제품 화면에서 확인해야 하는 UI 이름은 필요한 경우 영문과 함께 표기합니다.
- 영문 원본이 변경되면 이 문서의 동기화 절차에 따라 한국어 번역본을 갱신합니다.

## 2. 디렉터리 구조

```text
Instructions/
├─ Labs/       # 영문 원본
├─ Labs-kr/    # 한국어 번역본과 이 관리 문서
└─ media/      # 영문과 한국어 실습이 공동으로 사용하는 이미지
```

이미지, Office 문서, 빌드 설정 등은 한국어 번역 범위에 포함하지 않습니다.

## 3. 원본과 번역 파일의 대응 관계

| 영문 원본 | 한국어 번역 |
|---|---|
| `../Labs/00-ILT-setup.md` | `00-ILT-setup.md` |
| `../Labs/01-create-agents.md` | `01-create-agents.md` |
| `../Labs/02-manage-topics.md` | `02-manage-topics.md` |
| `../Labs/03-knowledge.md` | `03-knowledge.md` |
| `../Labs/04-workflow-tools.md` | `04-workflow-tools.md` |
| `../Labs/05-create-agent-new-experience.md` | `05-create-agent-new-experience.md` |

파일을 추가하거나 이름을 변경할 때는 영문과 한국어 디렉터리의 대응 관계를 유지합니다.

## 4. 번역 기준

### 4.1 기본 원칙

- 영문의 문장 구조를 그대로 옮기기보다 한국어 사용자가 이해하기 쉬운 문장으로 번역합니다.
- 수행 단계는 `~합니다` 형식으로 통일합니다.
- 원문에 없는 기능이나 절차를 추측하여 추가하지 않습니다.
- 실습 결과에 영향을 주는 값과 기술 식별자는 번역하지 않습니다.
- 제목, 단계, 목록, 표, 링크 및 이미지의 순서와 구조를 보존합니다. 원문의 코드 블록은 유지하고 입력 가능한 한국어 프롬프트 코드 블록을 추가할 수 있습니다.

### 4.2 문체

| 목적 | 표현 |
|---|---|
| 메뉴 또는 버튼 선택 | `~를 선택합니다.` |
| 값 입력 | `~를 입력합니다.` |
| 상태 확인 | `~가 표시되는지 확인합니다.` |
| 결과 설명 | `~가 생성됩니다.` |
| 가능성 안내 | `~할 수 있습니다.` |
| 필수 조건 | `~해야 합니다.` |

불필요한 존칭, 구어체 및 번역투를 피합니다.

### 4.3 제품 및 UI 용어

Microsoft 제품명은 번역하지 않습니다.

- Microsoft Copilot Studio
- Microsoft Copilot
- Microsoft Entra ID
- Microsoft Teams
- Power Platform
- Power Apps
- Power Automate
- Dataverse
- OneDrive
- Excel Online (Business)
- Adaptive Card
- Power Fx

현재 실습 이미지는 영어 UI를 사용하므로 화면에서 직접 찾아야 하는 주요 항목은 처음 등장할 때 한국어와 영문을 함께 표기합니다.

예:

- **에이전트(Agents)**
- **지식(Knowledge)**
- **도구(Tools)**
- **토픽(Topics)**
- **설정(Settings)**
- **게시(Publish)**
- **초안 저장(Save draft)**

같은 작업 안에서 반복되는 UI 이름은 문맥에 따라 간소화할 수 있습니다.

### 4.4 기본 용어

| 영어 | 한국어 |
|---|---|
| agent | 에이전트 |
| topic | 토픽 |
| knowledge source | 지식 소스 |
| tool | 도구 |
| workflow | 워크플로 |
| agent flow | 에이전트 흐름 |
| instruction | 지침 |
| prompt | 프롬프트 |
| authoring canvas | 작성 캔버스 |
| test pane | 테스트 창 |
| trigger | 트리거 |
| node | 노드 |
| variable scope | 변수 범위 |
| generative orchestration | 생성형 오케스트레이션 |
| generative answers | 생성형 답변 |
| grounded response | 근거 기반 응답 |
| fallback topic | 대체 토픽 |
| classic experience | 클래식 환경 |
| new experience | 새로운 환경 |

## 5. 프롬프트 처리 정책

프롬프트는 영문 원문과 한국어 번역문을 각각 복사 가능한 `prompt` 코드 블록으로 제공합니다. 학습자는 두 프롬프트 중 사용할 언어를 선택할 수 있습니다.

````markdown
다음 프롬프트 중 하나를 입력합니다.

```prompt
You are an agent that analyzes, categorizes, and prioritizes tasks.
```

```prompt
작업을 분석하고 분류하며 우선순위를 지정하는 에이전트입니다.
```
````

다음 규칙을 적용합니다.

- 에이전트 생성 프롬프트, 지침, 토픽 생성 프롬프트 및 테스트 메시지에 동일한 형식을 사용합니다.
- 영문과 한국어를 하나의 코드 블록에 함께 넣지 않습니다.
- 영문 프롬프트 다음에 한국어 프롬프트를 별도의 `prompt` 코드 블록으로 배치합니다.
- 두 언어 모두 복사하여 입력할 수 있도록 일반 인용문을 사용하지 않습니다.
- 프롬프트 안의 URL, 참조 이름 및 자리표시자는 원문을 유지합니다.
- Power Fx 수식이나 URL 설명처럼 입력 가능한 한국어 프롬프트가 아닌 보충 설명은 일반 인용문으로 유지합니다.

## 6. 번역하지 않는 요소

다음 요소는 기능과 후속 단계에 영향을 줄 수 있으므로 원문을 유지합니다.

- URL 및 파일 경로
- 스키마 이름
- 변수 이름
- 에이전트, 토픽 및 도구를 참조하는 식별자
- Power Fx 식
- Power Automate 식
- OData 필터
- 테이블과 열을 참조하는 기술 값
- 코드 블록의 언어 지정자

예:

```text
govbenefitsagent
insuranceagent
expenseagent
analyzetaskagent
Topic.Name
Topic.EmailAddress
Global.Priority
Text(Global.Priority)
Priority eq ''
string(outputs('List_rows_present_in_a_table')?['body/value'])
```

표시 이름이나 샘플 데이터가 후속 단계에서 다시 사용되는 경우에도 원문을 유지하고 필요하면 한국어 번역문을 제공합니다.

사용자가 직접 입력하거나 선택하는 사람 친화적인 이름, 제목 및 설명은 실제 영문 값을 유지하고, 영문 바로 뒤의 괄호 안에 한국어를 함께 표기합니다.

```markdown
**`US Benefits Assistant`(미국 복리후생 지원 담당자)**
```

괄호 안의 한국어는 이해를 돕기 위한 설명이며 실제 입력값에 포함하지 않습니다. 스키마 이름, 변수 이름, 수식, 필터, Excel 열 이름 및 선택값처럼 다른 단계에서 참조하는 값에는 이 방식을 적용하지 않습니다.

## 7. Markdown 및 YAML 보존 규칙

### 7.1 YAML front matter

YAML 키와 구조는 유지하고 사용자에게 표시되는 `title`, `module`, `description` 값만 번역합니다.

`duration`, `level`, `islab` 및 `primarytopics`의 구조와 제품명은 원문을 유지합니다.

### 7.2 Markdown

원본과 다음 항목을 일대일로 유지합니다.

- 제목 수준과 순서
- Exercise 및 Task 번호
- 단계 번호
- 목록과 표
- 코드 블록과 언어 지정자
- 링크와 이미지
- NOTE 및 IMPORTANT callout

## 8. 이미지 및 링크

- `../media`의 기존 이미지를 공동으로 사용합니다.
- 이미지 파일을 복사하거나 수정하지 않습니다.
- 이미지 경로는 변경하지 않고 대체 텍스트만 자연스러운 한국어로 번역합니다.
- URL과 상대 경로는 변경하지 않고 링크의 표시 문구만 번역합니다.
- 잘못된 경로나 오래된 외부 링크를 발견하면 임의로 수정하지 않고 알려진 문제로 기록합니다.

## 9. 영문 원본 동기화 절차

### 9.1 변경 범위 확인

마지막 동기화 커밋과 현재 커밋 사이에서 영문 실습의 변경 사항을 확인합니다.

```powershell
git diff <마지막-동기화-커밋>..HEAD -- Instructions\Labs
```

다음 변경을 구분하여 확인합니다.

- 추가, 삭제 또는 이름이 변경된 파일
- 추가되거나 삭제된 실습 단계
- 변경된 UI 레이블
- 변경된 프롬프트와 기술 값
- 변경된 이미지 및 링크

### 9.2 한국어 번역본 반영

- 영문 파일로 한국어 파일을 덮어쓰지 않습니다.
- 영문 diff를 의미 단위로 한국어 파일에 반영합니다.
- 새 프롬프트는 영문 원문과 한국어 번역문을 각각 별도의 `prompt` 코드 블록으로 추가합니다.
- 삭제된 단계는 대응하는 한국어 단계도 삭제합니다.
- 번호, 링크 또는 이미지가 바뀌면 한국어 파일에도 같은 구조 변경을 적용합니다.

### 9.3 검증 및 기준 갱신

- 변경된 파일의 제목, 단계, 이미지, 링크 및 코드 블록을 원본과 비교합니다.
- 기술 식별자와 영문 프롬프트가 보존되었는지 확인합니다.
- 모든 변경을 반영하고 검증한 후에만 동기화 기준 커밋과 검토일을 갱신합니다.
- 일부 변경만 반영한 상태에서는 기준 커밋을 갱신하지 않습니다.

## 10. 동기화 상태

| 파일 | 상태 | 원본 기준 커밋 | 마지막 검토일 |
|---|---|---|---|
| `00-ILT-setup.md` | 번역 완료 | `80591fd` | 2026-09-27 |
| `01-create-agents.md` | 번역 완료 | `80591fd` | 2026-09-27 |
| `02-manage-topics.md` | 번역 완료 | `80591fd` | 2026-09-27 |
| `03-knowledge.md` | 번역 완료 | `80591fd` | 2026-09-27 |
| `04-workflow-tools.md` | 번역 완료 | `80591fd` | 2026-09-27 |
| `05-create-agent-new-experience.md` | 번역 완료 | `80591fd` | 2026-09-27 |

- 기준 브랜치: `main`
- 최초 번역 기준 커밋: `80591fd`
- 최초 번역 시작일: `2026-09-27`

## 11. 검증 체크리스트

- [x] 영문과 한국어 실습 파일의 수와 이름이 대응하는가?
- [x] YAML front matter와 제목 구조가 유지되었는가?
- [x] Exercise, Task 및 단계 번호가 유지되었는가?
- [x] 이미지와 링크 참조가 유지되었는가?
- [x] 원문의 코드 블록과 언어 지정자가 유지되었는가?
- [x] 입력용 영문 프롬프트가 원문과 일치하는가?
- [x] 각 입력용 프롬프트에 복사 가능한 한국어 `prompt` 코드 블록이 있는가?
- [x] 변수, 스키마 이름, 식 및 필터가 변경되지 않았는가?
- [x] UI 용어가 일관되고 필요한 곳에 영문이 병기되었는가?
- [x] 사람 친화적인 영문 입력값에 한국어 설명이 코드 범위 밖에 병기되었는가?
- [x] 기존 `Instructions/Labs`와 다른 프로젝트 파일이 변경되지 않았는가?

## 12. GitHub Pages 게시

이 리포지토리는 `main` 브랜치의 루트 디렉터리를 GitHub Pages 소스로 사용합니다.

- 사이트: `https://hahaysh.github.io/mslearn-copilotstudio-kr/`
- 한국어 실습 경로: `https://hahaysh.github.io/mslearn-copilotstudio-kr/Instructions/Labs-kr/`
- 루트 `index.md`는 `Instructions/Labs-kr`의 한국어 실습만 목록에 표시합니다.
- 이 README에는 YAML front matter를 추가하지 않으며 실습 목록에 포함하지 않습니다.

Pages 설정은 GitHub 웹 화면 대신 `gh` CLI로 관리합니다.

```powershell
gh api repos/hahaysh/mslearn-copilotstudio-kr/pages
gh api repos/hahaysh/mslearn-copilotstudio-kr/pages/builds/latest
```

영문 원본을 갱신하고 한국어 번역본에 동기화한 뒤에는 변경 사항을 `main`에 푸시하고 Pages 빌드가 완료되었는지 확인합니다.

게시 후 다음 URL을 검증합니다.

```text
https://hahaysh.github.io/mslearn-copilotstudio-kr/Instructions/Labs-kr/00-ILT-setup.html
https://hahaysh.github.io/mslearn-copilotstudio-kr/Instructions/Labs-kr/01-create-agents.html
https://hahaysh.github.io/mslearn-copilotstudio-kr/Instructions/Labs-kr/02-manage-topics.html
https://hahaysh.github.io/mslearn-copilotstudio-kr/Instructions/Labs-kr/03-knowledge.html
https://hahaysh.github.io/mslearn-copilotstudio-kr/Instructions/Labs-kr/04-workflow-tools.html
https://hahaysh.github.io/mslearn-copilotstudio-kr/Instructions/Labs-kr/05-create-agent-new-experience.html
```

## 13. 알려진 원문 문제

다음 항목은 번역 과정에서 임의로 수정하지 않고 원문의 의미를 유지합니다.

- `05-create-agent-new-experience.md`는 사전 빌드 액션을 추가한다고 설명하지만 액션을 명시적으로 추가하고 구성하는 절차가 보이지 않습니다.
- `05-create-agent-new-experience.md`의 요약은 워크플로 도구 실습을 `Lab 03`으로 언급하지만 현재 파일 순서에서는 `04-workflow-tools.md`가 해당 내용을 다룹니다.
- `03-knowledge.md`의 비용 정책 다운로드 URL은 이 리포지토리가 아니라 MicrosoftLearning 원본 리포지토리를 가리킵니다.

문제를 수정해야 하는 경우 번역 동기화 작업과 분리하여 검토합니다.
