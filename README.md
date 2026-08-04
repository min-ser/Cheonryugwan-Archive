# Cheonryugwan Archive

> **천류관 : 흐름의 기록**  
> 원본 소설을 기준으로 세계관, 캐릭터, 기록, 복선, 이미지, 분석 결과와 모바일 인터랙티브 노벨을 함께 관리하는 장기 IP 프로젝트입니다.

현재 버전: **v0.3.0 — GitHub Pages Foundation**

## 목표

- 원본 소설과 창작 설정을 안전하게 관리
- 모바일 우선 반응형 웹/PWA 게임 제작
- 인기가 없어도 엔드투엔드 포트폴리오로 활용
- 반응이 있으면 상용 배포로 확장

## 정본 원칙

**작성자가 보유한 원본 소설이 최상위 Canon입니다.**

```text
원본 소설 → 승인된 Archive → 게임 데이터 → 웹/PWA 게임
```

대화 중 추측, 샘플 스토리, 테스트 데이터는 승인 전까지 공식 설정이 아닙니다.

## 아이디어 작성 위치

아이디어가 떠오르면 **`ideas/inbox/`에 먼저 작성**합니다. 정본 소설이나 설정집을 즉시 수정하지 않습니다.

- 채택: `ideas/accepted/`
- 보류: `ideas/parking/`
- 폐기: `ideas/rejected/`
- 주제별: `ideas/story/`, `ideas/characters/`, `ideas/world/`, `ideas/game/` 등
- 템플릿: `templates/IDEA_TEMPLATE.md`

## 원본 소설 위치

```text
story/_INBOX/
```

분석 결과는 다음에 분리합니다.

- `story/_ANALYZED/`
- `story/_REPORTS/`
- `story/_CONFLICTS/`

원본은 삭제하거나 덮어쓰지 않습니다.

## ZIP 보관 위치

```text
archives/source-zips/       원본 ZIP
archives/generated/         릴리즈·보고서·분석 결과
archives/backups/           로컬·대규모 변경 전 백업
```

세부 경로:

- 소설 ZIP: `archives/source-zips/story/`
- 이미지 ZIP: `archives/source-zips/images/`
- 참고 ZIP: `archives/source-zips/references/`
- 릴리즈 ZIP: `archives/generated/releases/`

대용량 ZIP은 Git에서 제외하고 로컬 백업, 개인 클라우드 또는 GitHub Release를 권장합니다.

## 캐릭터 설정과 이미지

- 원본 설정: `archive/characters/<character-id>/`
- 배포 이미지: `game/assets/images/characters/<character-id>/`

## VS Code 실행

1. 프로젝트 폴더 열기
2. 추천 확장 `Live Server` 설치
3. `game/index.html` 우클릭 → **Open with Live Server**

예상 주소: `http://127.0.0.1:5500/game/index.html`

## Git 계정 확인

```bash
git config user.name
git config user.email
git log --format="%h %an <%ae>"
```

회사 계정, 회사 장비, 회사 AI 계정, 고객 자료를 개인 프로젝트에 사용하지 않습니다.

## 라이선스와 저작권

- 소프트웨어 코드: MIT License (`LICENSE`)
- 소설·캐릭터·세계관·대사·이미지·로고 등: All Rights Reserved
- 상세 정책: `COPYRIGHT.md`
- 요약 고지: `NOTICE`

## 주요 문서

- `docs/PROJECT_STANDARD.md`
- `docs/CANON.md`
- `docs/NAMING_RULE.md`
- `docs/STORY_STANDARD.md`
- `docs/IMAGE_STANDARD.md`
- `docs/VERSION_POLICY.md`
- `docs/GIT_WORKFLOW.md`
- `docs/IDEA_WORKFLOW.md`
- `docs/ARCHIVE_STORAGE_GUIDE.md`

## v0.2.0 완료

- [x] LICENSE / COPYRIGHT / NOTICE 분리
- [x] Canon 및 프로젝트 표준
- [x] 아이디어 Inbox와 상태 관리
- [x] 원고 분석·보고서·충돌 폴더
- [x] ZIP 원본·릴리즈·백업 구조
- [x] VS Code Live Server 설정
- [x] `.gitignore` 보강
- [x] README 전면 개편
- [ ] 실제 소설 원본 분석
- [ ] 실제 캐릭터 이미지 연결
- [ ] 본편 게임 데이터 변환

## 다음 버전

**v0.3.0 — Story Intake**: 실제 원고의 파일 목록, 메타데이터, 구조, 인물, 세력, 시간 순서, 충돌 후보를 정리합니다.


## GitHub Pages 웹사이트

v0.3.0부터 저장소 루트의 `index.html`이 프로젝트 랜딩 페이지로 동작합니다.

```text
/
├── index.html                 프로젝트 메인
├── game/                      실제 인터랙티브 노벨
├── pages/archive/             Archive 안내
├── pages/story/               Story Intake 안내
├── pages/characters/          Character Archive
├── pages/world/               World Bible
├── pages/roadmap/             개발 진행 상황
└── pages/about/               프로젝트 소개
```

GitHub Pages를 저장소의 `main` 브랜치 `/root`로 설정하면 다음 형태로 접속합니다.

```text
https://<github-id>.github.io/Cheonryugwan-Archive/
```

게임 직접 주소:

```text
https://<github-id>.github.io/Cheonryugwan-Archive/game/
```

### GitBlog/Portfolio 저장소에 복사하는 경우

다음 폴더 전체를 원하는 경로에 복사하면 됩니다.

```text
Portfolio/Project/Cheonryugwan-Archive/
```

예상 주소:

```text
https://<github-id>.github.io/Portfolio/Project/Cheonryugwan-Archive/
```

모든 내부 링크는 상대 경로를 사용하므로 동일한 폴더 구조를 유지해야 합니다.

## v0.3.0 완료 체크리스트

- [x] GitHub Pages용 루트 랜딩 페이지
- [x] 모바일 반응형 공통 Header/Footer
- [x] Home, Game, Archive, Story, Characters, World, Roadmap, About 내비게이션
- [x] Story Intake 상태 페이지
- [x] Archive 안내 페이지
- [x] Character Archive 플레이스홀더
- [x] World Bible 플레이스홀더
- [x] 개발 로드맵 페이지
- [x] License/Copyright 안내 페이지
- [x] 루트 PWA Manifest 및 Service Worker
- [x] GitBlog/Portfolio 복사 배포 가이드
- [ ] 실제 원본 소설 분석
- [ ] 실제 캐릭터 이미지 연결
- [ ] 실제 Archive 데이터 공개
