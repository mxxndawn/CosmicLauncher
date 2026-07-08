# AGENTS.md

## Project Rules

- 수정 전 현재 구조를 먼저 파악한다.
- 대규모 리팩터링은 요청받기 전까지 하지 않는다.
- 기존 스타일과 네이밍을 유지한다.
- 보안 관련 파일, 환경변수, 인증 로직은 임의로 변경하지 않는다.
- 변경 후 가능한 경우 테스트 또는 빌드 명령을 실행한다.

## Commands

```bash
npm install
npm start
npm run dist
npm run dist:win
npm run dist:mac
npm run dist:linux
```