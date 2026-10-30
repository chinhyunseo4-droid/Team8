<!-- BEGIN:nextjs-agent-rules -->

## This is NOT the Next.js you know

This version has breaking changes — APIs, conventions, and file structure may all differ from your training data. Read the relevant guide in `node_modules/next/dist/docs/` (resolved from this file's directory; in monorepos the `next` package may not be visible from the repo root) before writing any code. Heed deprecation notices.

This block is written and re-added by `next dev` — verify at `node_modules/next/dist/server/lib/generate-agent-files.js`. Removing it from a diff only re-creates the uncommitted change; committing it with your work keeps the tree clean.

<!-- END:nextjs-agent-rules -->

# Team8 해커톤 개발 규칙

## 1. 프로젝트 기본 정보

- 프로젝트 이름: team8
- 프로젝트 최상위 폴더: team8/
- 서비스 기획서: docs/PROJECT.md
- 개발 목표: 제한된 해커톤 시간 안에 핵심 기능이 정상 작동하는 MVP 완성

작업 전 서비스 기획서와 현재 프로젝트 구조를 확인한다.

## 2. 기술 스택

- 프론트엔드: Next.js (App Router) + React + TypeScript
- 백엔드: Next.js Route Handlers 및 필요한 Server Actions
- 데이터베이스: Supabase (PostgreSQL)
- 사용자 인증: Supabase Auth (필요한 경우)
- 스타일링: Tailwind CSS
- AI 개발 도구: OpenAI Codex

다음 원칙을 따른다.

- 기존 기술 스택을 최대한 재사용한다.
- 특별한 이유가 없다면 FastAPI, Express 등 별도 백엔드 서버를 추가하지 않는다.
- 새로운 라이브러리는 필요한 경우에만 도입한다.
- Next.js 관련 코드를 작성하기 전에 설치된 버전의 관련 문서를 확인한다.

## 3. 개발 기본 원칙

### 3-1. 빠른 MVP 개발

- 완벽한 아키텍처보다 실제로 작동하는 핵심 기능 구현을 우선한다.
- 불필요한 추상화, 과도한 리팩터링, 복잡한 설계는 피한다.
- 기존에 구현된 컴포넌트와 기능을 최대한 재사용한다.
- 사용자가 특별히 요구하지 않은 부가 기능은 임의로 추가하지 않는다.

### 3-2. 기능별 독립 개발

- 기능별로 파일과 컴포넌트를 분리한다.
- 프론트엔드와 백엔드 간 API 요청 및 응답 형식을 명확히 정의한다.
- 공용 API와 TypeScript 타입을 일관되게 유지한다.
- 팀원이 각자 담당 기능을 독립적으로 개발할 수 있도록 한다.
- 다른 팀원의 작업 영역은 승인 없이 변경하지 않는다.

### 3-3. 자율적인 개발

다음 작업은 허용된 작업 범위와 실행 권한 안에서 Codex가 자율적으로 수행한다.

- 담당 기능의 코드 작성 및 수정
- UI 컴포넌트 생성
- API 구현
- 일반적인 오류 수정
- 관련 테스트 및 빌드 실행
- 작은 규모의 코드 정리
- 사소한 구현 방식 결정

중요한 보안 문제나 팀 전체에 영향을 주는 구조 변경을 제외하면 매번 사용자에게 확인을 요청하지 않는다.

## 4. 필수 제한 사항 (Guardrails)

다음 규칙은 반드시 준수한다.

### 4-1. 보안

- API 키, 비밀번호, Secret Key를 코드나 Git에 노출하지 않는다.
- .env.local 등의 민감정보 파일을 Git에 커밋하지 않는다.
- 데이터베이스 인증 및 접근 권한 정책을 임의로 우회하지 않는다.
- 서비스의 보안 기능을 임의로 제거하거나 비활성화하지 않는다.

### 4-2. 데이터 보호

- 운영 데이터베이스 및 실제 사용자 데이터를 임의로 삭제하거나 초기화하지 않는다.
- 파괴적인 데이터베이스 명령을 실행하기 전에 승인을 요청한다.
- 기존 데이터베이스 스키마 변경이 필요한 경우 먼저 변경 내용을 설명한다.

### 4-3. 팀 협업

- 공용 API 규격을 승인 없이 변경하지 않는다.
- 다른 팀원의 담당 기능을 임의로 수정하지 않는다.
- Git 강제 푸시(force push) 및 공유 커밋 기록 재작성을 하지 않는다.
- 공용 설정이나 핵심 의존성을 변경할 경우 변경 내용을 사전에 알린다.

## 5. 코드 검증

- 기능 구현 후 관련 테스트를 실행한다.
- 가능한 경우 TypeScript 타입 검사, Lint 및 Build를 수행한다.
- 문제가 발생하면 원인을 분석하고 담당 범위 내에서 수정한다.
- 테스트하지 않은 기능을 정상 작동한다고 보고하지 않는다.
- 오류를 숨기기 위해 테스트나 보안 검사를 임의로 비활성화하지 않는다.
- 담당 기능과 관련 없는 파일은 가급적 수정하지 않는다.

## 6. 작업 결과 보고

작업 완료 후 다음 내용을 간결하게 보고한다.

1. 구현 또는 수정한 기능
2. 변경한 주요 파일
3. 테스트 및 검증 결과
4. 해결하지 못한 문제
5. 다른 팀원이 알아야 할 API 또는 설정 변경사항

불필요하게 긴 설명보다는 실제 결과와 필요한 정보를 우선한다.

## 7. 프로젝트 기획서 확인

- 작업 시작 전 docs/PROJECT.md를 확인한다.
- 서비스의 핵심 목표와 MVP 범위를 기준으로 개발한다.
- 기획서에 없는 중요한 기능은 임의로 확정하지 않는다.
- PROJECT.md에 '미정'으로 표시된 사항은 확정된 요구사항으로 간주하지 않는다.
- 불명확한 사항은 합리적인 가정을 세워 진행하되, 핵심 요구사항에 영향을 주는 경우 사용자에게 확인한다.

## 8. 승인 요청 기준

- 일반적인 코드 작성, 수정 및 오류 해결은
  허용된 작업 범위 내에서 자율적으로 수행한다.
- 공용 API, 데이터베이스 스키마, 인증 구조,
  다른 팀원의 코드 변경이 필요하면 승인을 요청한다.
- 보안상 금지된 작업은 실행하지 않으며,
  필요한 경우 안전한 대안을 제시한다.
- 실행 권한이 부족한 작업은 권한 우회 없이
  승인 요청 또는 대체 방법을 제안한다.
- 사소한 구현 결정에는 승인을 요청하지 않는다.


### 실행하면 좋을듯한 내용이 있으나 규칙에 위반되어 실행하지 못한다면 반드시 실행 허가 여부를 질문하도록 한다. 