# README 생성 체계 지침

이 문서는 대상 레포지토리에 재사용 가능한 README 생성 체계를 만들거나 갱신하기 위한 한국어 기준 문서입니다.

이 문서를 대상 레포지토리에 그대로 복사하지 않습니다. 적용 가능한 규칙을 대상 레포지토리의 실제 맥락에 맞게 `AGENTS.md`, `resources/README.preset.md`, README 생성 명령으로 재작성해서 대상 레포지토리만으로 이해되고 유지보수될 수 있게 만듭니다.

## 레퍼런스 사용 규칙

사용자가 이 문서를 레퍼런스하라고 지시했다는 것은 이 문서의 적용 가능한 지침을 따르라는 뜻입니다. 이 문서의 구조, 제목, 예시, 파일 배치, 저장소 고유 표현을 복사하라는 뜻이 아닙니다.

대상 레포지토리의 실제 파일, 언어, 도구, 관례에 맞게 규칙을 적용합니다. 사용자가 명시적으로 요청하지 않는 한 앞으로도 `readme-md`, 이 파일, 원본 저장소를 계속 참고하라는 문구를 남기지 않습니다.

## 언어 정책

사용자가 명시한 언어를 우선합니다.

사용자가 언어를 지정하지 않았다면 아래 근거로 대상 `AGENTS.md`의 언어를 추론합니다.

- 사용자 메시지의 언어
- 대상 레포지토리의 README와 docs에서 주로 쓰는 언어
- issue, docs, 주석, contributing 문서에서 확인되는 주요 작업 또는 의사소통 언어
- 레포지토리 내용에서 명확히 드러나는 제품 또는 프로젝트 locale

언어를 추론할 수 없으면 영어를 기본값으로 사용합니다.

에이전트는 기본적으로 추론한 사용자 선호 언어로 응답합니다. 대상 레포지토리가 이미 다국어 지침을 사용하거나 사용자가 다국어 출력을 요청한 경우가 아니라면 대상 `AGENTS.md` 안에서 언어를 섞지 않습니다.

사용자가 언어별 지침 파일을 요청하면 대상 루트 `AGENTS.md`는 짧은 영문 라우터로 두고, 세부 지침은 `agents/AGENTS.<locale>.md`에 둡니다. 예시는 `agents/AGENTS.kr.md`입니다. 명시적 요청 없이 이 다국어 라우팅 구조를 대상 레포지토리에 도입하지 않습니다.

## 범위

목표는 단일 `README.md` 파일만 작성하는 것이 아닙니다. 목표는 대상 레포지토리 안에 재현 가능한 README 생성 체계를 만들거나 갱신하는 것입니다.

적용 범위는 README 관련 산출물로 제한합니다.

- 생성 결과물인 `README.md`
- README source-of-truth, 일반적으로 `resources/README.preset.md`
- 필요한 경우 README 생성 명령 또는 스크립트
- 히어로를 사용하는 경우 README 히어로 원본과 생성 결과물
- 대상 `AGENTS.md`의 README 유지보수 지침
- README 생성 명령을 실제로 만들었고 대상에 `package.json`, `Makefile`, `justfile` 같은 명령 목록이 있는 경우 해당 목록 연결

이 레퍼런스 저장소의 응답 스타일, 커밋 원칙, 브랜치 원칙, 배포 절차, 로컬 작업 방식, 개인 프로젝트 성격, 파일 구조를 대상 레포지토리의 일반 규칙으로 가져가지 않습니다.

## 복사하지 말아야 할 것

사용자가 명시적으로 요청하지 않는 한 대상 레포지토리에 아래를 추가하지 않습니다.

- 앞으로도 `readme-md`를 계속 참고하라는 문장
- 레퍼런스 저장소의 로컬 경로, GitHub URL, 저장소명
- `자세한 내용은 이 저장소를 참고` 같은 문구
- 레퍼런스 저장소의 README 문장을 대상 프로젝트 소개처럼 사용하는 것
- 이 문서의 섹션 순서를 대상 `AGENTS.md` 구조로 그대로 쓰는 것
- 이 저장소의 생성 결과물인 `resources/readme-hero.svg`
- 이 저장소의 고유 히어로 이미지 파일인 `resources/hero.png`, `resources/hero.light.png`, `resources/hero.dark.png` 등
- 생성 체계를 요청받았는데 source-of-truth 없는 단일 `README.md`만 두는 것
- README 생성과 무관한 대상 코드, 배포, 운영, 설정 재작성

적용 결과는 대상 레포지토리만 clone해도 이해되어야 합니다.

## 초기 확인

대상 README 생성 체계를 만들거나 갱신하기 전에 대상 레포지토리를 먼저 확인합니다.

최소한 아래를 확인합니다.

- `git status --short`
- 기존 루트와 하위 `AGENTS.md`
- 기존 `CLAUDE.md`
- 기존 `README.md`
- docs, contributing 문서, 운영 노트
- `package.json`, `pyproject.toml`, `Cargo.toml`, `go.mod`, `Gemfile` 같은 패키지 manifest와 lockfile
- 설정 파일, CI 파일, script 디렉터리
- `package.json`, `Makefile`, `justfile` 같은 명령 목록 존재 여부
- 실제 사용 언어, 프레임워크, 런타임, 패키지 매니저
- 생성 파일과 수동 원본 파일의 source-of-truth 관계
- 사용 가능한 빌드, 테스트, 린트, 포맷, README 생성 명령

확인하지 않은 기술, 명령어, 배포 방식, 조직명, 비공개 URL, 파일 경로를 사실처럼 쓰지 않습니다.

## 새 대상 체계 적용 순서

대상 레포지토리에 README 생성 체계를 새로 만들 때는 아래 순서를 따릅니다.

1. 대상의 지침 파일을 먼저 읽습니다. `AGENTS.md`, 하위 `AGENTS.md`, `CLAUDE.md`, README, docs, contributing 문서를 확인합니다.
2. 기존 대상 `README.md`를 입력 자료로 사용하기 전에, 레퍼런스 저장소의 `PRESET.md` 구조를 대상 `resources/README.preset.md`의 초기 골격으로 먼저 고정합니다.
3. 히어로 체계를 사용할 경우 레퍼런스 `resources/readme-hero.preset.svg`만 대상 레포지토리로 복사합니다.
4. 그 다음 `package.json`, lockfile, `.nvmrc`, 설정 파일, docs, scripts를 확인합니다.
5. 기존 대상 `README.md`가 있으면 프리셋 골격을 고정한 뒤에만 읽습니다. 프로젝트 역할, 실행 방법, 생성 파일, 수정 기준 같은 확인된 사실만 추출합니다.
6. 고정한 프리셋 골격에 대상 레포지토리의 확인된 사실을 채웁니다.
7. 자동 재생성이 필요하면 대상 레포지토리 형태에 맞는 단순하고 재현 가능한 생성 명령 또는 스크립트를 둡니다.
8. 대상 레포지토리에 명령 목록이 있고 README 생성 명령을 만들었다면 그 목록에 등록합니다.
9. 생성된 `README.md` 상단에는 생성 파일임을 알리는 주석을 둡니다.
10. 대상 `AGENTS.md`에 README 유지보수 규칙을 추가합니다.

이 과정에서 레퍼런스 저장소를 링크하거나 계속 참조하라고 안내하지 않습니다.

## 템플릿 적용 강제 규칙

기존 대상 `README.md`는 사실 확인용 자료일 뿐입니다. 템플릿이 아닙니다.

`resources/README.preset.md`는 대상의 기존 README가 아니라 레퍼런스 `PRESET.md` 구조에서 시작해야 합니다. 작업 방식은 프리셋의 placeholder, 섹션, 히어로 블록, 생성 파일 주석에 대상 레포지토리의 확인된 사실을 채워 넣는 것입니다.

아래 규칙을 지킵니다.

1. 기존 대상 `README.md`를 구조 판단용으로 열기 전에, 레퍼런스 `PRESET.md` 구조를 대상 `resources/README.preset.md` 초안으로 둡니다.
2. generated-file comment, hero block, title/description/badge 영역, 목차와 H2 anchor 패턴, 레포지토리 구성 섹션의 plaintext tree 형식을 보존합니다.
3. 대상 파일에서 확인한 사실을 각 섹션에 채웁니다.
4. 기존 README의 H2 순서, 목차, badge 배치, 이미지 위치, 문장 흐름을 새 구조로 사용하지 않습니다.
5. 기존 README 구조가 더 좋아 보인다는 판단이 들면 작업을 멈추고 프리셋 구조로 다시 작성합니다.

기존 README에 좋은 설명이 있으면 구조를 복사하지 말고 의미 기준으로 옮깁니다.

- 프로젝트 소개는 역할 또는 개요 섹션에 다시 씁니다.
- 설치, 실행, 빌드, README 생성 명령은 확인된 경우에만 시작하기 또는 스크립트 섹션에 넣습니다.
- 기존 목차는 버리고 최종 H2 섹션 기준으로 다시 만듭니다.
- badge는 실제 기술 스택과 링크가 확인되는 경우에만 다시 구성합니다.
- 대상 프로젝트의 핵심 기술 스택 badge를 우선합니다.
- 대상 레포지토리 버전이나 배포 상태가 중요하면 레포지토리/버전/상태 badge와 기술 스택 badge를 줄로 분리합니다.
- 기존 히어로나 이미지 배치는 그대로 복사하지 말고 `resources/hero.*`와 `resources/readme-hero.preset.svg` 흐름으로 연결합니다.
- 레포지토리 구성은 표나 산문만으로 쓰지 않고 `plaintext` tree 코드블록으로 작성합니다.

`PRESET.md`와 `resources/readme-hero.preset.svg`는 시작 골격입니다. 대상 레포지토리에 맞지 않는 선택 섹션은 삭제하고 필요한 섹션은 추가할 수 있지만, 히어로 블록, 생성 파일 주석, source-of-truth 관계, README 생성 계약을 재설계하지 않습니다.

아래 결과가 나오면 적용 실패로 보고 다시 작성합니다.

- `resources/README.preset.md`의 초기 구조가 기존 대상 `README.md`와 같은 경우
- 기존 README의 H2 순서, 목차, badge 영역, 이미지 배치를 보존한 경우
- 프리셋의 히어로 블록이나 생성 파일 주석이 사라진 경우
- 레포지토리 구성 섹션이 `plaintext` tree가 아니라 표나 산문인 경우
- `resources/README.preset.md`가 기존 README를 약간 고친 파일처럼 보이는 경우

## 대상 산출물 조건

대상 README 생성 체계에는 적용 가능한 범위에서 아래가 있어야 합니다.

- 상단 주석으로 생성 결과물임을 표시한 `README.md`
- `resources/README.preset.md` 또는 이에 준하는 README source-of-truth
- 히어로를 사용하는 경우 히어로 wrapper source-of-truth인 `resources/readme-hero.preset.svg`
- 히어로 체계를 사용하는 경우 생성된 `resources/readme-hero.svg`
- 자동 재생성이 필요한 경우 `scripts/readme_update.sh` 또는 이에 준하는 생성 명령
- 대상에 `package.json`, `Makefile`, `justfile` 같은 명령 목록이 있고 README 생성 명령을 만들었다면 해당 목록 등록
- README 변경이 생성 결과물 직접 수정이 아니라 원본 수정에서 시작한다는 문서화
- 대상 `AGENTS.md`의 README 유지보수 지침

아래 상태로 남기지 않습니다.

- 새로 작성하거나 덮어쓴 `README.md`만 있는 경우
- 기존 대상 `README.md`를 그대로 `resources/README.preset.md`로 옮긴 경우
- README 본문에 생성 규칙을 설명했지만 source-of-truth 파일이 없는 경우
- 기존 명령 목록이 있는데 README 생성 명령을 등록하지 않은 경우
- 대상 `AGENTS.md`, scripts, 설정 파일을 확인하지 않고 일반 템플릿을 붙여 넣은 경우
- 대상 README 또는 `AGENTS.md`가 `readme-md`를 계속 참조해야만 이해되는 경우

## 기존 대상 체계 갱신 기준

대상 레포지토리에 이미 `AGENTS.md`, `resources/README.preset.md`, README 생성 스크립트, 생성된 `README.md`가 있다면 보존적 갱신으로 처리합니다.

이 레퍼런스와 구조가 다르다는 이유만으로 대상의 기존 지침 체계를 교체하지 않습니다.

아래 규칙을 따릅니다.

- 기존 대상 `AGENTS.md`의 언어, 섹션 구조, 저장소 역할, 명령어, 검증 기준, 금지사항을 가능한 한 보존합니다.
- 실패를 막는 데 필요한 README 생성 규칙만 추가하거나 병합합니다.
- 대상 고유 규칙을 일반 레퍼런스 문구보다 우선합니다.
- 대상 고유 규칙과 이 레퍼런스가 충돌하면 충돌을 보고하고, 사용자 승인 없이 대상 규칙을 제거하지 않습니다.
- 의미를 보존할 수 있는 중복 규칙은 병합합니다.
- 확인하지 못한 명령어, 링크, 배포 절차, 생성 파일 관계는 사실처럼 고쳐 쓰지 말고 확인 필요 항목으로 분리합니다.
- 사용자가 명시적으로 요청하지 않았다면 루트/언어별 파일 라우팅 구조를 대상 레포지토리에 도입하지 않습니다.
- 기존 README source-of-truth가 이미 정상 작동한다면 사용자가 명시적으로 마이그레이션을 요청하지 않는 한 보존합니다.
- 기존 README 생성 명령이 있다면 경쟁 명령을 새로 만들지 말고 해당 명령을 갱신합니다.
- 기존 생성 파일 주석이나 히어로 규칙이 있다면 대상 맥락에서 가능한 범위만 이 레퍼런스와 정렬합니다.

갱신 후 가능한 경우 `git diff --check`, `git status --short`, 대상 README 생성 명령을 실행합니다.

## 대상 AGENTS.md에 추가할 README 규칙

대상 `AGENTS.md`에는 README 수정 방법을 독립적으로 이해할 수 있게 설명해야 합니다. 아래 규칙 중 적용 가능한 내용을 포함합니다.

- `README.md`는 생성 결과물이며 직접 수정으로 끝내지 않습니다.
- README 내용을 바꿀 때는 `resources/README.preset.md` 또는 대상 레포지토리에서 정한 README source-of-truth를 수정합니다.
- 기존 `README.md`는 사실 확인용 자료로만 사용합니다. 그 구조나 문장 흐름을 `resources/README.preset.md`의 템플릿으로 삼지 않습니다.
- README 원본은 프리셋 구조에 대상 레포지토리의 확인된 사실을 채워 넣는 방식으로 유지합니다.
- 기존 README 구조와 프리셋 구조가 충돌하면 사용자가 명시적으로 달리 요청하지 않는 한 프리셋 구조를 우선합니다.
- README 원본의 placeholder, 경로, 섹션 구조가 바뀌면 README 생성 명령이나 스크립트도 함께 갱신합니다.
- 자동 재생성이 필요하면 원본 수정 후 `scripts/readme_update.sh` 또는 대상 레포지토리의 지정 생성 명령을 실행합니다.
- 자동 재생성 명령이 필요 없으면 대상 `AGENTS.md`에는 원본 수정 기준만 남기고 불필요한 스크립트나 README 스크립트 섹션을 만들지 않습니다.
- 대상에 `package.json`, `Makefile`, `justfile` 같은 명령 목록이 있고 README 생성 명령을 만들었다면 그 목록에 등록합니다.
- 의미 있는 스크립트가 여러 개 있으면 README에 스크립트 섹션을 구성하고, README 생성 명령이 있으면 포함합니다.
- README 관련 변경을 이유로 대상 코드, 설정, 배포, 운영 지침을 임의로 리팩터링하거나 재작성하지 않습니다.
- README H1 제목은 `resources/README.preset.md`에 최종 문구를 직접 작성합니다.
- 생성 명령이나 스크립트가 `package.json` 이름, 디렉터리명, git remote, `${projectName}`, `${displayName}` 같은 placeholder로 H1 제목을 생성하거나 덮어쓰지 않게 합니다.
- 대상 `resources/README.preset.md`에 H1 placeholder를 남기지 않습니다.
- H1 규칙은 스크립트 검증만으로 해결할 문제가 아니라 에이전트가 원본 작성 시 지켜야 할 작성 규칙입니다.
- README의 한 줄 설명은 중앙 정렬 description block에 최종 문구로 직접 작성합니다. `${description}` placeholder를 남기지 않고 스크립트가 생성하거나 덮어쓰지 않게 합니다.
- 히어로 이미지 `alt` 텍스트도 README 원본에 최종 문구로 직접 작성합니다. `${projectName} hero image` 같은 placeholder를 남기지 않고 스크립트가 생성하거나 덮어쓰지 않게 합니다.
- 레포지토리 구성 섹션은 임의의 표가 아니라 `plaintext` 코드블록 tree로 작성합니다.
- 목차가 있으면 H2 섹션 추가, 삭제, 이름 변경에 맞춰 목차를 갱신합니다.
- 문서 내부 링크, badge 링크, 이미지 링크는 대상 레포지토리 기준의 상대 경로 또는 검증된 공개 URL로 유지합니다.
- badge는 확인된 핵심 기술, 패키지 매니저, 배포 상태, 레포지토리 버전 정보에만 추가합니다.
- runtime, language, framework, package manager, documentation format처럼 독자가 프로젝트 성격을 빠르게 파악하는 데 도움이 되는 badge를 우선합니다.
- 레포지토리 버전이나 배포 상태가 중요하면 첫 줄은 레포지토리/버전/상태, 둘째 줄은 기술 스택으로 나눕니다.
- badge를 추가하거나 제거할 때는 README 원본과 생성된 README를 함께 갱신합니다.
- `resources/readme-hero.preset.svg`를 재설계하지 않습니다.
- 레퍼런스 저장소에서 히어로 지원을 위해 복사할 파일은 `resources/readme-hero.preset.svg`뿐입니다. 생성된 히어로 결과물이나 고유 이미지 파일은 복사하지 않습니다.
- README 생성 명령은 `resources/readme-hero.preset.svg`에서 `resources/readme-hero.svg`를 만들고, 실제 존재하는 `hero.png`, `hero.jpg`, `hero.light.*`, `hero.dark.*` 이미지만 base64 data URI로 내장해야 합니다.
- 생성된 `resources/readme-hero.svg` 내부 fallback text `readme-md`는 대상 레포지토리 이름으로 교체합니다.
- 커스텀 히어로는 `resources/hero.png`로 추가합니다.
- 모드별 히어로가 필요하면 `resources/hero.light.png`, `resources/hero.dark.png`를 추가합니다.
- H2 제목은 섹션 구분이 쉬워지도록 의미가 맞는 이모지 1개로 시작합니다.
- 태그, badge, 목차, 섹션 이름, 섹션 순서, 포함 여부는 대상 레포지토리의 실제 필요에 맞게 조정합니다.
- secret, token, credential, 비공개 내부 URL은 README와 README 원본에 기록하지 않습니다.
- README 생성 명령, 링크, badge, 이미지 상태는 실제로 확인하지 않았다면 검증했다고 쓰지 않습니다.
- README에는 확인된 사실만 쓰고 외부 템플릿 저장소에 대한 의존 문구를 남기지 않습니다.

## 레포지토리 형태별 분기

대상 레포지토리의 실제 사실을 기준으로 README 섹션과 메타데이터를 결정합니다.

- `package.json`이 있으면 확인 후 `name`, `version`, `packageManager`, `scripts`, `repository`를 README 메타데이터로 사용할 수 있습니다.
- `package.json`이 없으면 패키지명, 패키지 버전, 패키지 매니저 badge를 만들지 않습니다.
- 일반 Git 레포지토리는 확인 후 디렉터리명과 git remote를 기본 메타데이터로 사용할 수 있습니다.
- 문서 전용 레포지토리는 설치와 빌드보다 문서 역할, 편집 원칙, 수정 절차를 우선합니다.
- monorepo 또는 workspace는 루트 README와 하위 프로젝트 README의 역할을 분리합니다.
- 대상 레포지토리 자체 도구에 필요하지 않다면 레퍼런스식 README 체계를 위해 `package.json`을 추가하지 않습니다.

## README.preset.md 구조

대상 `resources/README.preset.md`는 먼저 레퍼런스 `PRESET.md` 구조에서 만들고, 그 안에 대상 레포지토리의 확인된 사실을 채웁니다.

`PRESET.md`는 에이전트용 구조 프리셋입니다. 대상 레포지토리에서 실제 source-of-truth 파일은 `resources/README.preset.md` 또는 대상이 정한 동등한 원본 파일입니다.

프리셋은 단순 예시가 아니라 시작 골격입니다. 대상 레포지토리에 맞지 않는 선택 섹션은 삭제하고 필요한 섹션은 추가할 수 있지만, 기존 README를 따라가기 위해 source-of-truth 모델을 바꾸지 않습니다.

대상 레포지토리가 사용자-facing 문서로 명시적으로 필요로 하지 않는 한 `README 수정 방법`을 주요 H2 섹션으로 두지 않습니다. 생성 파일 주석과 대상 `AGENTS.md` 유지보수 지침에 두는 것을 우선합니다.

레퍼런스 저장소에서만 의미 있는 항목은 그대로 가져가지 않습니다. 예를 들어 `./scripts/readme_update.sh`는 레퍼런스 저장소의 핵심 명령이지만, 대상 레포지토리에서는 자동 README 재생성이 필요할 때만 사용합니다.

대상 레포지토리에 의미 있는 스크립트가 여러 개 있으면 README 스크립트 섹션을 구성합니다. 노출할 스크립트가 없거나 별도 생성 명령이 필요 없으면 해당 섹션과 목차 항목을 생략합니다.

레포지토리 구성 섹션은 반드시 `plaintext` 코드블록 tree를 사용합니다. 대상 레포지토리에 실제로 없는 항목은 삭제하고 중요한 원본 파일, 생성 결과물, 진입점, 설정 파일만 남깁니다.

## README 섹션 기준

아래를 기본 골격으로 삼고 대상 레포지토리에 맞게 조정합니다.

- Hero and title: 최종 H1, 한 줄 설명, 레포지토리/버전/상태 badge, 기술 스택 badge.
- Role: 레포지토리가 하는 일과 하지 않는 일.
- Getting started: runtime, package manager, install, run, build 명령. 확인된 경우에만 작성합니다.
- Main workflow: 생성, 빌드, 배포, 운영 반영 흐름. 관련 있을 때만 작성합니다.
- Repository structure: 중요한 디렉터리와 생성 파일. 반드시 `plaintext` tree로 작성합니다.
- Scripts: 실제 실행 가능한 명령. 노출할 것이 없으면 생략합니다.
- Modification method: 원본 파일과 생성 명령. 일반적으로 user-facing 주요 H2가 아니라 주석과 대상 `AGENTS.md`에 둡니다.
- Collaboration notes: 대상에 필요한 경우 `AGENTS.md`, 생성 파일 원칙, 커밋/배포 주의사항.

## 히어로 이미지 규칙

히어로 체계를 사용할 때는 아래를 따릅니다.

- 레퍼런스 저장소의 `resources/readme-hero.preset.svg`를 대상 히어로 wrapper 원본으로 복사합니다.
- 레퍼런스 저장소의 생성된 히어로 결과물이나 고유 히어로 이미지 파일은 복사하지 않습니다.
- wrapper를 재설계하거나 별도 SVG/HTML/CSS 히어로 체계를 만들지 않습니다.
- README 생성 명령은 `resources/readme-hero.preset.svg`를 읽어 `resources/readme-hero.svg`를 생성합니다.
- 생성 시 fallback text `readme-md`를 대상 레포지토리 이름으로 교체합니다.
- 실제 존재하는 대상 파일만 base64 data URI로 내장합니다.
  - `resources/hero.png`
  - `resources/hero.jpg`
  - `resources/hero.light.png`
  - `resources/hero.light.jpg`
  - `resources/hero.dark.png`
  - `resources/hero.dark.jpg`
- 존재하지 않는 히어로 이미지 파일의 `<image>` 태그는 생성된 SVG에서 제거합니다.
- 기본 커스텀 히어로를 쓰려면 `resources/hero.png`를 추가하라고 안내합니다.
- 모드별 히어로가 필요하면 `resources/hero.light.png`, `resources/hero.dark.png`를 추가하라고 안내합니다.
- 프리셋 이미지 순서상 `hero.light.*`, `hero.dark.*`는 각 모드에서 `hero.png` 또는 `hero.jpg` 위에 그려집니다. 모드별 이미지가 한쪽 모드만 덮어야 한다면 다른 모드를 위해 기본 `hero.png` 또는 `hero.jpg`를 유지합니다.
- `.jpg` 파일도 존재하면 사용할 수 있지만 기본 안내는 `.png` 파일명을 우선합니다.
- README 원본과 생성된 README는 `resources/readme-hero.svg`를 참조하고, 커스텀 이미지는 `hero.*` 파일 추가 후 생성 명령을 실행하라는 주석을 둡니다.

## 문서 작성 기준

README는 새 작업자가 레포지토리를 빠르게 이해하고 작업을 시작하는 데 필요한 정보를 우선합니다.

- 프로젝트가 하는 일과 하지 않는 일을 분리합니다.
- H2 제목은 섹션 구분에 도움이 되면 의미 있는 이모지 1개로 시작합니다.
- 태그, badge, 목차, 섹션 이름, 섹션 순서, 포함 여부는 레포지토리에 맞게 조정합니다.
- 확인된 경우 핵심 기술 badge를 포함합니다.
- 레포지토리 버전이나 배포 상태가 중요하면 레포지토리/버전/상태 badge와 기술 스택 badge를 분리합니다.
- 작은 문서 전용 레포지토리는 목차를 짧게 쓰거나 생략합니다.
- 라이브러리, 앱, 운영 레포지토리는 필요에 따라 사용법, API, 배포, 운영 섹션을 나눕니다.
- README 히어로는 생성된 `resources/readme-hero.svg`로 로드하고, `resources/readme-hero.preset.svg`를 수동 재설계하지 않습니다.
- 한 줄 설명과 히어로 `alt` 텍스트는 `resources/README.preset.md`에 placeholder 없이 최종 문구로 작성합니다.
- 다크/라이트 히어로 파일은 필요할 때만 추가합니다.
- `resources/readme-hero.svg`의 fallback text는 이미지 레이어 뒤의 대상 레포지토리 이름으로 둡니다.
- fallback 배경색은 라이트 모드에서 `#00224411`, 다크 모드에서 `#000C18CE`를 사용합니다.
- 설치, 실행, 빌드, README 생성 명령은 실제 script나 명령이 확인된 경우에만 작성합니다.
- 생성 파일과 수동 수정 원본 파일을 구분합니다.
- 레포지토리 구성은 표가 아니라 tree 코드블록으로 작성합니다.
- 운영이나 배포 절차가 있으면 실제 반영 지점과 확인 절차를 씁니다.
- 외부 링크는 필요한 경우에만 사용하고, 깨질 가능성이 큰 링크는 피합니다.
- 회사명, 제품명, 내부 용어는 대상 레포지토리에서 필요한 경우에만 사용합니다.
- 저장소별 사실과 범용 규칙을 섞지 않습니다.
- 문서 원본과 생성 스크립트의 placeholder, 경로, embedded text가 수동 동기화 관계라면 둘 다 갱신합니다.

## 검증

대상 레포지토리에 체계를 적용한 뒤 가능한 관련 확인을 실행합니다.

우선순위는 아래와 같습니다.

- 생성하거나 수정한 대상 README 생성 명령
- `git diff --check`
- `git status --short`
- 대상 레포지토리에 이미 문서화된 관련 검증 명령

환경 설정, 권한, 누락된 의존성, 누락된 파일 때문에 명령을 실행할 수 없다면 이유를 명확히 보고합니다. 실행하지 않은 명령이 성공했다고 말하지 않습니다.

## 완료 보고

간결하게 보고합니다.

1. 변경 요약
2. 변경 파일
3. 실행한 검증 명령과 결과
4. 남은 위험, 한계, 후속 필요 사항

문서만 변경했다면 그 사실을 명시합니다.

기존 대상 `AGENTS.md`나 README 생성 체계를 갱신한 경우 아래를 분리해 보고합니다.

- 보존한 기존 대상 규칙
- 새로 적용한 규칙
- 충돌 또는 확인 필요 항목
- 검증 결과
