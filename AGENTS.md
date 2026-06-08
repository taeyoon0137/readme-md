# readme-md 작업 지침

이 저장소에서는 아래 기준을 우선합니다. 사용자가 별도로 다른 지시를 내리면 최신 사용자 지시를 따릅니다.

## 🚀 먼저 읽기

다른 레포지토리에 README 생성 체계를 만들기 위해 이 파일을 열었다면 이 문서 전체를 읽지 않습니다. 아래 섹션만 읽고, README.md와 README 생성 로직에 관한 내용만 대상 레포지토리에 독립적으로 적용합니다.

- [🔄 다른 레포지토리에 적용할 때](#다른-레포지토리에-적용할-때)
- [템플릿 적용 강제 규칙](#템플릿-적용-강제-규칙)
- [적용 산출물 조건](#적용-산출물-조건)
- [대상 AGENTS.md에 추가할 README 수정 지침](#대상-agentsmd에-추가할-readme-수정-지침)
- [레포지토리 형태별 분기 기준](#레포지토리-형태별-분기-기준)
- [대상 README.preset.md 구성 템플릿](#대상-readmepresetmd-구성-템플릿)
- [README 섹션 구성 기준](#readme-섹션-구성-기준)
- [히어로 이미지 적용 기준](#히어로-이미지-적용-기준)
- [문서 작성 기준](#문서-작성-기준)

위 섹션의 내용을 대상 레포지토리 안의 `AGENTS.md`, `resources/README.preset.md`, 필요한 생성 명령으로 재작성합니다. 이 저장소의 응답 원칙, 커밋 원칙, 로컬 운영 방식, 프로젝트 성격, 디렉터리 구조 등 README 생성과 직접 관련 없는 내용은 절대로 대상 레포지토리에 반영하지 않습니다. 대상 레포지토리의 결과물에는 `readme-md`를 계속 참조하라는 문구를 남기지 않습니다.

이 저장소 자체를 수정하는 경우에만 아래의 유지보수 지침 전체를 함께 읽습니다.

## 💬 기본 응답 원칙

- 항상 한국어 존댓말로 응답합니다.
- 결론을 먼저 말하고, 확인하지 못한 내용은 명확히 분리합니다.
- 불필요한 칭찬, 감탄, 장식적 표현은 사용하지 않습니다.
- 사용자가 명시적으로 요청하지 않으면 commit, push, release, branch 생성 또는 branch 전환을 하지 않습니다.
- 이미 수정된 파일이 있으면 사용자 또는 이전 작업의 변경으로 간주하고 임의로 되돌리지 않습니다.
- 요청과 직접 관련 없는 리팩터링이나 구조 변경을 하지 않습니다.
- 실행하거나 확인하지 못한 명령어, 생성 결과, 파일 상태를 성공한 것처럼 보고하지 않습니다.

## 🧭 저장소 역할

`readme-md`는 이태윤의 개인 프로젝트에서 README 생성 방식을 표준화하기 위한 템플릿 저장소입니다.

- 특정 회사, 제품, 운영 환경의 문서를 담는 저장소가 아닙니다.
- 다른 에이전트가 대상 레포지토리에 README 생성 로직을 만들 때 이 구조와 규칙을 독립적으로 이식하기 위한 템플릿을 제공합니다.
- 이 저장소의 지침을 적용하는 작업의 목표는 단일 `README.md` 파일 작성이나 외부 참조 추가가 아니라, 대상 레포지토리 안에 재생성 가능한 README 생성 체계를 만드는 것입니다.
- `AGENTS.md`는 이 저장소 자체의 작업 지침이면서, 대상 레포지토리의 README 수정 지침을 만들기 위한 기준입니다.
- `CLAUDE.md`는 별도 파일로 복제하지 않고 `AGENTS.md`를 가리키는 심볼릭 링크로 유지합니다.
- README source-of-truth는 `resources/README.preset.md`입니다.
- `README.md`는 생성 결과물입니다.

## 🚫 적용 금지 사항

대상 레포지토리에 이 템플릿을 적용할 때 아래를 하지 않습니다.

- README.md, README source-of-truth, README 생성 명령, 히어로 리소스, 대상 `AGENTS.md`의 README 수정 지침 외의 영역에 이 저장소 기준을 반영하지 않습니다.
- 대상 레포지토리의 README, AGENTS, docs에 `readme-md`를 참고하라고 쓰지 않습니다.
- 대상 레포지토리의 README, AGENTS, docs에 이 저장소의 로컬 경로, GitHub URL, 저장소명을 남기지 않습니다.
- “자세한 기준은 이 저장소를 참고” 같은 외부 참조 문구를 남기지 않습니다.
- 이 저장소의 README 문장을 그대로 복사해 대상 레포지토리 소개처럼 사용하지 않습니다.
- 대상 레포지토리에 이미 있던 `README.md`를 템플릿화하거나, 그 구조를 `resources/README.preset.md`의 기준으로 삼지 않습니다.
- 대상 레포지토리의 기존 `README.md`를 README source-of-truth로 승격하지 않습니다.
- 대상 레포지토리의 기존 `README.md`를 읽고 나서 그 모양을 따라 `resources/README.preset.md`를 만들지 않습니다.
- 이 저장소의 `PRESET.md`, `resources/readme-hero.preset.svg`, 히어로 블록, 생성 파일 주석, 생성 로직 계약을 임의로 재설계하지 않습니다.
- 단일 `README.md`만 작성하고 source-of-truth 없이 끝내지 않습니다.
- 이 저장소의 기본 응답 원칙, 커밋 원칙, 브랜치/배포 방식, 개인 프로젝트 성격, 파일 구조를 대상 레포지토리의 일반 작업 지침으로 가져가지 않습니다.

필요한 규칙은 대상 레포지토리 안의 `AGENTS.md`, `resources/README.preset.md`, 필요한 생성 명령에 맞게 재작성합니다. 적용 결과는 대상 레포지토리만 있어도 이해되고 실행되어야 합니다.

## 🔎 작업 시작 체크

작업 시작 시 다음을 먼저 확인합니다.

- `git status --short`
- `README.md`가 아니라 `resources/README.preset.md`가 source of truth인지 여부
- `CLAUDE.md`가 `AGENTS.md`를 가리키는 심볼릭 링크인지 여부
- 대상 레포지토리에 `package.json`이 있는지 여부
- 변경 대상이 지침, 프리셋, 생성 명령, 이미지 리소스 중 어디에 속하는지
- 참고해야 할 별도 문서나 프리셋이 있는지 여부

## 📚 주요 참고 문서

- `AGENTS.md`: 이 저장소의 작업 지침과 대상 레포지토리에 이식할 README 수정 지침의 기준입니다.
- `PRESET.md`: 대상 레포지토리의 `resources/README.preset.md`를 만들 때 참고하는 프리셋입니다.
- `resources/README.preset.md`: 이 저장소 `README.md`의 source-of-truth입니다.
- `scripts/readme_update.sh`: 이 저장소 `README.md`를 재생성하는 명령입니다.
- `resources/readme-hero.preset.svg`: 대상 레포지토리에 복사할 히어로 SVG 원본 wrapper입니다.
- `resources/readme-hero.svg`: `readme-hero.preset.svg`와 존재하는 `hero.*` 이미지를 기준으로 생성되는 README 히어로 결과물입니다.

세부 내용을 다른 파일에 이미 적었다면 `AGENTS.md`에 그대로 복제하지 않고, 어떤 작업에서 어느 파일을 먼저 봐야 하는지만 명시합니다.

## 📝 README 생성 규칙

`README.md`는 직접 수정으로 끝내지 않습니다.

대상 레포지토리에 이 지침을 적용할 때도 단일 `README.md` 파일만 작성하고 끝내지 않습니다. 반드시 README source-of-truth를 두고, 자동 재생성이 필요한 경우 생성 명령을 함께 둡니다.

1. `resources/README.preset.md`를 수정합니다.
2. `resources/README.preset.md`의 placeholder, 경로, 섹션 구조가 바뀌면 `./scripts/readme_update.sh`의 치환/생성 로직도 함께 수정합니다.
3. `resources/readme-hero.preset.svg` 또는 `resources/hero.*`가 바뀌면 `./scripts/readme_update.sh`의 히어로 SVG 생성 로직도 함께 확인합니다.
4. `./scripts/readme_update.sh`를 실행해 `README.md`와 `resources/readme-hero.svg`를 재생성합니다.

README에는 확인된 사실만 씁니다. 추측, 임시 운영 정보, secret, token, 개인 인증 정보는 포함하지 않습니다.

대상 레포지토리에 생성되는 README와 AGENTS에는 특별한 사용자 지시가 없는 한 `readme-md`, 이 저장소의 경로, 이 저장소의 GitHub URL, “이 저장소를 참고/참조” 같은 외부 의존 문구를 남기지 않습니다.

## 🔄 다른 레포지토리에 적용할 때

대상 레포지토리에서 에이전트에게 요청할 때는 아래처럼 짧게 말합니다.

```text
https://github.com/taeyoon0137/readme-md 의 AGENTS.md 기준으로,
이 레포지토리 안에 독립적으로 동작하는 README 생성 체계를 만들어줘.
```

대상 레포지토리에 README 생성 로직을 만들 때는 반영 범위를 README.md, README source-of-truth, README 생성 명령, 히어로 리소스, 대상 `AGENTS.md`의 README 수정 지침으로 제한하고 아래 순서를 따릅니다.

1. 대상 레포지토리의 `AGENTS.md`를 먼저 읽습니다.
2. 대상 레포지토리의 기존 `README.md`를 열기 전에, 이 저장소의 `PRESET.md` 구조를 대상 `resources/README.preset.md`의 초기 골격으로 고정합니다.
3. `resources/readme-hero.preset.svg`도 대상 레포지토리로 복사해 히어로 wrapper 원본을 먼저 고정합니다.
4. 그 다음 `package.json`, lockfile, `.nvmrc`, 설정 파일, docs, scripts를 확인합니다.
5. 기존 `README.md`가 있으면 이 단계에서만 열고, 구조를 가져오지 말고 프로젝트 역할, 실행 방법, 생성 파일, 수정 기준 같은 확인된 사실만 추출합니다.
6. README 원본은 이미 고정한 `PRESET.md` 골격 안에 대상 레포지토리의 확인된 사실을 채워 넣는 방식으로만 작성합니다.
7. README 자동 재생성이 필요하면 생성 스크립트나 명령을 단순하고 재현 가능하게 작성하며, 대상 레포지토리 형태에 따라 분기할 수 있게 둡니다.
8. 대상 레포지토리에 `package.json` 같은 script manifest가 있고 README 생성 명령을 만들었다면 해당 scripts 목록에 포함합니다.
9. `README.md` 상단에는 생성 파일임을 알리는 주석을 둡니다.

이 단계에서 이 저장소를 링크하거나 계속 참조하라고 안내하지 않습니다. 대상 레포지토리만 clone해도 README 생성과 수정 절차가 이해되고 실행되어야 합니다.

### 템플릿 적용 강제 규칙

대상 레포지토리에 이미 `README.md`가 있더라도 그 파일은 사실 확인용 입력 자료일 뿐입니다. 기존 README의 섹션 구조, 문장 흐름, 목차, 배지, 이미지 배치, 주석 형식을 기준 템플릿으로 사용하지 않습니다.

`resources/README.preset.md`는 반드시 이 저장소의 `PRESET.md`를 기준 골격으로 삼아 작성합니다. 작업 방식은 기존 README를 변환하는 것이 아니라, `PRESET.md`의 placeholder, 섹션, 히어로 블록, 생성 파일 주석에 대상 레포지토리의 확인된 내용을 채워 넣는 것입니다.

반드시 아래 순서를 지킵니다.

1. 기존 `README.md`를 열기 전에 `PRESET.md` 구조를 대상 `resources/README.preset.md`의 초안으로 둡니다.
2. `PRESET.md`의 generated-file comment, hero block, title/description/badge 영역, 목차와 H2 anchor 패턴, `레포지토리 구성` tree 형식을 먼저 유지합니다.
3. 그 후 대상 레포지토리의 파일과 기존 README에서 확인한 사실을 각 섹션에 채웁니다.
4. 기존 README의 섹션 순서나 표현이 더 좋아 보여도 구조 판단에 사용하지 않습니다.
5. 기존 README 구조를 따르고 싶다는 판단이 들면 작업을 멈추고, 이 템플릿 구조로 다시 작성합니다.

기존 README에 좋은 설명이 있으면 그대로 템플릿화하지 말고 아래처럼 옮깁니다.

- 프로젝트 소개는 `역할` 또는 대상 레포지토리에 맞는 소개 섹션에 재작성합니다.
- 설치, 실행, 빌드 명령은 `시작하기` 또는 `스크립트` 섹션에 확인된 명령으로 정리합니다.
- 기존 목차는 버리고, 최종 H2 섹션 기준으로 새 목차를 만듭니다.
- 기존 배지는 실제 기술 스택과 링크가 확인되는 경우에만 새 badge 영역에 다시 구성합니다.
- badge 영역에는 대상 프로젝트에서 실제로 쓰는 주요 기술 스택을 포함합니다.
- 대상 레포지토리 자체의 버전 정보가 사용자에게 중요한 경우에는 레포지토리/버전 badge 줄과 주요 기술 스택 badge 줄을 분리합니다.
- 기존 이미지나 히어로는 그대로 가져오지 말고 `resources/hero.*` 입력 파일과 `readme-hero.preset.svg` 생성 흐름으로 다시 연결합니다.
- 기존 레포지토리 구성 설명이 표로 되어 있더라도 그대로 가져오지 말고, `PRESET.md`의 `plaintext` tree 샘플에 실제 파일 구조를 채워 넣습니다.

`PRESET.md`와 `resources/readme-hero.preset.svg`는 적용 골격입니다. 대상 레포지토리의 성격에 맞지 않는 선택 섹션을 삭제하거나 필요한 섹션을 추가할 수는 있지만, 히어로 블록, 생성 파일 주석, source-of-truth 구조, README 생성 명령 계약을 임의로 바꾸지 않습니다. 기존 README 구조와 이 템플릿 구조가 충돌하면 이 템플릿 구조를 우선합니다.

아래 결과가 나오면 적용 실패로 보고 즉시 다시 작성합니다.

- `resources/README.preset.md`의 첫 구조가 기존 `README.md`와 같은 경우
- 기존 README의 H2 순서, 목차, 배지 영역, 이미지 배치를 그대로 보존한 경우
- `PRESET.md`에 있는 히어로 블록이나 생성 파일 주석이 사라진 경우
- `레포지토리 구성`이 `plaintext` tree가 아니라 표나 산문으로 작성된 경우
- `resources/README.preset.md`가 “기존 README를 약간 수정한 파일”처럼 보이는 경우

### 적용 산출물 조건

대상 레포지토리에 README 생성 로직을 만들 때는 아래 구조를 갖춥니다.

- `README.md`가 생성 파일임을 상단 주석으로 명시합니다.
- `resources/README.preset.md` 또는 이에 준하는 source-of-truth 파일이 있습니다.
- 히어로를 사용하는 경우 `resources/readme-hero.preset.svg`를 source-of-truth로 두고, 생성 명령이 `resources/readme-hero.svg`를 만듭니다.
- 자동 재생성이 필요하면 `scripts/readme_update.sh` 또는 대상 레포지토리의 도구 체계에 맞는 생성 명령이 있습니다.
- 대상 레포지토리에 `package.json`, `Makefile`, `justfile` 같은 명령 목록이 있고 README 생성 명령을 만들었다면 그 목록에도 등록되어 있습니다.
- README 수정 방법이 `README.md` 직접 수정이 아니라 원본 수정 기준으로 문서화되어 있습니다.
- 대상 레포지토리의 `AGENTS.md`에 README 수정 지침이 추가되어 있습니다.

아래 구조는 사용하지 않습니다.

- `README.md` 파일 하나만 새로 작성하거나 덮어쓴 경우
- 대상 레포지토리의 기존 `README.md`를 그대로 `resources/README.preset.md`로 옮기거나, 기존 README 구조를 기준으로 프리셋을 만든 경우
- README 본문에 생성 규칙을 설명했지만 원본 파일이 없는 경우
- 대상 레포지토리에 script 목록이 있고 README 생성 명령도 만들었지만 그 목록에는 연결하지 않은 경우
- 대상 레포지토리의 `AGENTS.md`, script, 설정 파일을 확인하지 않고 일반 템플릿을 붙여 넣은 경우
- 대상 레포지토리의 README나 AGENTS가 `readme-md`를 계속 참조해야 동작하거나 이해되는 경우

### 대상 AGENTS.md에 추가할 README 수정 지침

이 템플릿을 적용한 대상 레포지토리의 `AGENTS.md`에는 README를 어떻게 수정해야 하는지 독립적으로 이해할 수 있는 지침을 추가합니다. 지침에는 최소한 아래 내용을 포함합니다.

- `README.md`는 생성 파일이며 직접 수정으로 끝내지 않습니다.
- README 내용을 바꿀 때는 `resources/README.preset.md` 또는 대상 레포지토리에서 정한 README source-of-truth를 수정합니다.
- 기존 `README.md`는 사실 확인용 자료로만 사용하고, 그 구조나 문장 흐름을 `resources/README.preset.md`의 템플릿으로 삼지 않습니다.
- README 원본은 정해진 프리셋 구조에 확인된 내용을 채워 넣는 방식으로 유지하며, 기존 README 구조와 프리셋 구조가 충돌하면 프리셋 구조를 우선합니다.
- `README.preset.md`의 placeholder, 경로, 섹션 구조가 바뀌면 README 생성 명령이나 스크립트의 치환/생성 로직도 반드시 함께 수정합니다.
- 자동 재생성이 필요한 레포지토리라면 원본을 수정한 뒤 `scripts/readme_update.sh` 또는 대상 레포지토리에서 정한 생성 명령을 실행해 `README.md`를 재생성합니다.
- 자동 재생성 명령이 필요 없으면 대상 `AGENTS.md`에 원본 수정 기준만 남기고 별도 스크립트나 README의 스크립트 섹션은 만들지 않습니다.
- 대상 레포지토리에 `package.json`, `Makefile`, `justfile` 같은 명령 목록이 있고 README 생성 명령을 만들었다면 그 목록에 포함되어야 합니다.
- 복수의 의미 있는 스크립트가 있는 레포지토리라면 README에 주요 스크립트 목록을 구성하고, README 생성 명령을 만들었다면 그 목록에 포함합니다.
- README 관련 변경을 이유로 대상 레포지토리의 코드, 설정, 배포, 운영 지침을 임의로 리팩터링하거나 재작성하지 않습니다.
- README의 `레포지토리 구성` 섹션은 임의의 표로 만들지 않고, `plaintext` 코드블록 tree로 작성합니다.
- README 목차를 둔 경우 H2 섹션 추가, 삭제, 이름 변경에 맞춰 목차와 anchor 링크를 함께 갱신합니다.
- 문서 내부 링크, badge 링크, 이미지 링크는 대상 레포지토리 기준의 상대 경로 또는 공개 URL로 유지합니다.
- badge는 대상 레포지토리의 실제 주요 기술 스택, 패키지 매니저, 배포 상태, 버전 정보가 확인되는 경우에만 추가합니다.
- badge 영역에는 프로젝트의 핵심 기술 스택을 우선 포함합니다. 예를 들어 런타임, 언어, 프레임워크, 패키지 매니저, 문서 포맷처럼 README 독자가 프로젝트 성격을 빠르게 파악하는 데 필요한 기술을 넣습니다.
- 대상 레포지토리 자체의 버전이나 배포 상태가 중요한 프로젝트라면 badge 영역을 두 줄로 나눕니다. 첫 줄은 레포지토리/버전/배포 상태, 둘째 줄은 주요 기술 스택으로 구성합니다.
- badge를 추가하거나 제거할 때는 README 상단 badge 영역과 README 원본을 함께 갱신합니다.
- 히어로 wrapper 원본인 `resources/readme-hero.preset.svg`는 임의로 재작성하지 않습니다.
- 이 저장소에서 가져갈 히어로 관련 원본 파일은 `resources/readme-hero.preset.svg`뿐이며, `resources/readme-hero.svg`, `resources/hero.png`, `resources/hero.light.png`, `resources/hero.dark.png` 같은 생성 결과물이나 고유 이미지 파일은 복사하지 않습니다.
- README 생성 명령은 `resources/readme-hero.preset.svg`를 기반으로 `resources/readme-hero.svg`를 생성해야 하며, 존재하는 `hero.png`, `hero.jpg`, `hero.light.*`, `hero.dark.*` 이미지만 base64 data URI로 내장합니다.
- `resources/readme-hero.svg` 생성 시 SVG 내부 fallback text인 `readme-md`는 대상 레포지토리 이름으로 교체합니다.
- 커스텀 히어로 이미지는 `resources/hero.png`를 추가해 적용합니다.
- 라이트/다크 모드별 히어로가 필요하면 `resources/hero.light.png`, `resources/hero.dark.png`를 추가합니다.
- H2 제목은 섹션 구분이 쉽도록 의미가 맞는 이모지 1개로 시작합니다.
- 태그, badge, 목차, 섹션 이름, 섹션 순서, 포함 여부는 대상 레포지토리의 성격에 맞게 유연하게 조정합니다.
- secret, token, credential, 비공개 내부 URL은 README와 README 원본에 기록하지 않습니다.
- 실행하거나 확인하지 못한 생성 명령, 링크, badge, 이미지 상태를 성공한 것처럼 쓰지 않습니다.
- README에는 확인된 사실만 쓰고, 추측이나 외부 템플릿 저장소에 대한 의존 문구를 남기지 않습니다.

### 레포지토리 형태별 분기 기준

- `package.json`이 있으면 `name`, `version`, `packageManager`, `scripts`, `repository`를 README 생성 메타데이터로 사용할 수 있습니다.
- `package.json`이 없으면 패키지명, 패키지 버전, 패키지 매니저 badge를 만들지 않습니다.
- 일반 git 레포지토리는 디렉터리명과 git remote를 기본 메타데이터로 사용합니다.
- 문서 전용 레포지토리는 설치/빌드보다 문서 역할, 편집 원칙, 수정 절차를 우선합니다.
- monorepo 또는 workspace는 루트와 하위 프로젝트의 README 역할을 분리합니다.
- 이 저장소 자체에는 `package.json`을 두지 않습니다.

### 대상 README.preset.md 구성 템플릿

대상 레포지토리의 `resources/README.preset.md`는 이 저장소의 README나 대상 레포지토리의 기존 README를 기반으로 만들지 않습니다. 반드시 [`PRESET.md`](./PRESET.md)의 구조를 먼저 대상 `resources/README.preset.md`의 골격으로 두고, 그 안에 대상 레포지토리의 확인된 내용을 채워 넣습니다.

`PRESET.md`는 에이전트가 읽는 구조 프리셋 파일입니다. 실제 적용 시에는 대상 레포지토리 안에 `resources/README.preset.md` 파일을 생성합니다.

위 템플릿은 기본 골격이 아니라 먼저 고정해야 하는 시작 골격입니다. 대상 레포지토리에 맞지 않는 선택 섹션은 삭제하고, 필요한 섹션은 추가할 수 있지만, 기존 README의 구조를 따라가기 위한 변경은 허용하지 않습니다. `README 수정 방법`은 주요 H2 섹션으로 두지 않고, 생성 파일 주석과 대상 `AGENTS.md`의 README 수정 지침에 둡니다.

이 저장소에서만 의미 있는 항목은 대상 README에 그대로 가져가지 않습니다. 예를 들어 이 저장소에서 `./scripts/readme_update.sh`는 핵심 실행 명령이지만, 대상 레포지토리에서는 자동 재생성이 필요할 때만 둘 README 생성 명령입니다.

대상 레포지토리에 복수의 의미 있는 스크립트가 있으면 README의 `스크립트` 섹션을 구성합니다. README에 노출할 스크립트가 없거나 별도 생성 명령이 필요 없으면 해당 섹션과 목차 항목은 생략합니다. Node 계열 레포지토리에서 README 생성 명령을 만들었다면 `package.json`의 `scripts`에도 추가합니다.

`레포지토리 구성` 섹션은 반드시 `PRESET.md`의 `plaintext` 코드블록 tree 샘플을 기준으로 작성합니다. 표로 바꾸거나 산문으로만 설명하지 않습니다. 대상 레포지토리에 실제로 없는 항목은 삭제하고, source-of-truth, 생성 결과물, 실행 진입점, 중요한 설정 파일만 남깁니다.

### README 섹션 구성 기준

아래 항목은 기본 뼈대이며, 대상 레포지토리에 맞게 줄이거나 늘립니다.

- Hero/Title: 프로젝트 이름, 한 줄 설명, 레포지토리/버전/상태 badge와 주요 기술 스택 badge
- 역할: 이 레포지토리가 무엇을 하고 무엇을 하지 않는지
- 시작하기: 런타임, 패키지 매니저, 설치와 실행 명령어
- 주요 흐름: 생성, 빌드, 배포, 운영 반영 같은 핵심 workflow
- 레포지토리 구성: 중요한 디렉터리와 생성 파일의 위치. 반드시 `plaintext` tree 코드블록으로 작성하고 표로 만들지 않습니다.
- 스크립트: 대상 레포지토리의 실제 실행 명령 목록. 노출할 명령이 없으면 생략합니다.
- 수정 방법: README 원본과 필요한 경우 생성 명령어. 본문 H2가 아니라 주석과 `AGENTS.md` 지침에 둡니다.
- 공동작업 지침: `AGENTS.md`, 생성 파일 원칙, 커밋/배포 주의사항

### 히어로 이미지 적용 기준

- 대상 레포지토리에 적용할 때 `resources/readme-hero.preset.svg`는 이 저장소의 파일을 그대로 복사해 사용합니다.
- 이 저장소의 `resources/readme-hero.svg`, `resources/hero.png`, `resources/hero.light.png`, `resources/hero.dark.png`, `resources/hero.jpg` 같은 생성 결과물이나 고유 히어로 이미지 파일은 대상 레포지토리로 복사하지 않습니다.
- 에이전트가 `resources/readme-hero.preset.svg`를 새로 디자인하거나, 임의의 SVG/HTML/CSS hero wrapper를 생성하지 않습니다.
- README 생성 명령은 `resources/readme-hero.preset.svg`를 읽어 `resources/readme-hero.svg`를 생성합니다.
- 생성 시 `resources/readme-hero.preset.svg` 내부 fallback text인 `readme-md`는 대상 레포지토리 이름으로 교체합니다.
- 생성 시 대상 레포지토리에 실제 존재하는 `resources/hero.png`, `resources/hero.jpg`, `resources/hero.light.png`, `resources/hero.light.jpg`, `resources/hero.dark.png`, `resources/hero.dark.jpg`만 base64 data URI로 `resources/readme-hero.svg` 안에 내장합니다.
- 존재하지 않는 히어로 이미지의 `<image>` 태그는 생성된 `resources/readme-hero.svg`에서 제거합니다.
- 사용자가 임의의 히어로 이미지를 쓰고 싶다면 `resources/hero.png`를 추가하고 README 생성 명령을 다시 실행하도록 안내합니다.
- 라이트/다크 모드별 이미지가 필요하면 `resources/hero.light.png`, `resources/hero.dark.png`를 추가하고 README 생성 명령을 다시 실행하도록 안내합니다.
- JPG만 있는 경우에는 같은 이름의 `.jpg` 파일을 사용할 수 있지만, 기본 안내는 PNG 파일명을 우선합니다.
- `README.preset.md`와 생성된 `README.md`의 히어로 블록에는 `readme-hero.svg`를 그대로 참조하고, 커스텀 이미지는 `hero.*` 파일 추가 후 생성 명령을 실행하라는 주석을 남깁니다.

## ✍️ 문서 작성 기준

README는 새 작업자가 빠르게 프로젝트를 이해하고 작업을 시작하는 데 필요한 정보를 우선합니다.

- 프로젝트가 하는 일과 하지 않는 일을 구분합니다.
- H2 제목은 섹션 구분이 쉽도록 의미가 맞는 이모지 1개로 시작합니다.
- 태그, badge, 목차, 섹션 이름, 섹션 순서, 포함 여부는 대상 레포지토리의 성격에 맞게 유연하게 조정합니다.
- badge 영역에는 대상 프로젝트의 주요 기술 스택을 포함하고, 레포지토리 자체 버전이 중요한 경우 레포지토리/버전 badge와 기술 스택 badge를 줄로 분리합니다.
- 작은 문서 전용 레포지토리는 목차를 짧게 쓰거나 생략할 수 있고, 라이브러리/앱/운영 레포지토리는 사용법, API, 배포, 운영 반영 섹션을 더 세분화할 수 있습니다.
- README 히어로 이미지는 생성된 `resources/readme-hero.svg`를 통해 로드하고, 원본 wrapper인 `resources/readme-hero.preset.svg`는 임의로 재작성하지 않습니다.
- 다크/라이트 모드 전용 히어로가 필요하면 `resources/hero.dark.png`, `resources/hero.dark.jpg`, `resources/hero.light.png`, `resources/hero.light.jpg`를 추가합니다.
- `resources/readme-hero.svg` 중앙에는 레포지토리 이름을 fallback text로 두고, 이미지 레이어가 그 뒤에 있는 텍스트를 덮도록 배치합니다.
- `resources/readme-hero.svg`의 fallback 배경색은 라이트 모드에서 `#00224411`, 다크 모드에서 `#000C18CE`를 사용합니다.
- 설치, 실행, 빌드, README 생성 명령어는 실제 script가 있는 경우에만 작성합니다.
- 생성 파일과 수동 수정 파일을 분리해 설명합니다.
- 레포지토리 구성은 표가 아니라 tree 코드블록으로 작성해 파일과 디렉터리의 포함 관계를 드러냅니다.
- 운영이나 배포 절차가 있으면 실제 반영 위치와 확인 절차를 적습니다.
- 외부 링크는 필요한 경우에만 사용하고, 깨질 가능성이 큰 링크는 피합니다.
- 특정 회사명, 제품명, 내부 용어는 대상 레포지토리에서 필요한 경우에만 사용합니다.
- 저장소별로 달라지는 내용과 범용 원칙을 섞지 않습니다.
- 문서 원본과 생성 스크립트의 placeholder, 경로, embedded text가 수동 동기화 관계라면 둘 다 갱신합니다.

## ✅ 변경 후 확인 기준

이 저장소를 수정한 뒤 가능한 범위에서 아래를 확인합니다.

- `resources/README.preset.md`를 수정했다면 `./scripts/readme_update.sh`를 실행해 `README.md`를 재생성합니다.
- `resources/README.preset.md`의 placeholder, 경로, 섹션 구조를 바꿨다면 `scripts/readme_update.sh`의 치환/생성 로직도 함께 확인합니다.
- `resources/readme-hero.preset.svg` 또는 `resources/hero.*`를 수정했다면 `./scripts/readme_update.sh`를 실행해 `resources/readme-hero.svg`를 재생성합니다.
- `AGENTS.md`의 대상 레포지토리 적용 지침을 바꿨다면 `README.md`나 `PRESET.md`에 에이전트용 지침이 새어 들어가지 않았는지 확인합니다.
- `CLAUDE.md` 관련 작업을 했다면 `CLAUDE.md`가 `AGENTS.md`를 가리키는 심볼릭 링크인지 확인합니다.
- 실행하지 못한 명령이나 확인하지 못한 상태는 이유와 함께 보고합니다.

## 🧾 커밋 원칙

커밋은 사용자가 요청한 경우에만 합니다. 커밋을 만들 때는 역할과 목적별로 나눕니다.

- 문서 갱신: `Docs: ...`
- 설정 변경: `Config: ...`
- 생성 로직 변경: `Chore: ...`
- 버그 수정: `Fix: ...`

한 커밋에는 하나의 목적만 담습니다.
