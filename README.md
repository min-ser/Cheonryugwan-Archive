# Cheonryugwan Archive

> **천류관 : 흐름의 기록**  
> 세계관·캐릭터·소설 원문·기록·복선·게임 데이터를 하나의 저장소에서 관리하는 모바일 우선 인터랙티브 노벨 프로젝트입니다.

현재 버전: **v0.1.0 — Archive Foundation**

---

## 1. 프로젝트 원칙

### Archive First Principle

이 프로젝트에서 원본은 게임 코드가 아니라 **Archive와 Story 문서**입니다.

```text
세계관/캐릭터 설정
        ↓
소설 원문 작성
        ↓
스토리 분석 및 구조화
        ↓
게임용 JSON 변환
        ↓
모바일 웹 게임 반영
        ↓
테스트 및 배포
```

게임의 대사나 설정을 바꿀 때는 `game/data/`부터 직접 수정하지 않습니다.  
먼저 `archive/` 또는 `story/`의 원본 문서를 수정한 뒤 게임 데이터에 반영합니다.

---

## 2. 내가 작성한 소설은 어디에 넣는가?

기존에 작성한 소설 파일은 우선 아래 폴더에 넣습니다.

```text
story/_INBOX/
```

정리가 덜 된 초안, 여러 화가 합쳐진 문서, 메모, 텍스트 파일도 그대로 넣을 수 있습니다.

권장 형식:

- `.md`
- `.txt`
- `.docx`
- `.pdf`
- 기존 폴더가 포함된 `.zip`
- 참고 이미지 `.png`, `.jpg`, `.webp`

이미 파트와 장이 정리된 경우에는 다음 위치에 직접 배치합니다.

```text
story/
├── prologue/
├── part-01/
├── part-02/
├── part-03/
├── part-04/
├── side-stories/
├── drafts/
└── revisions/
```

파일명 권장 형식:

```text
NN-short-title.md
```

예시:

```text
01-the-unread-record.md
02-seo-harin-enters-the-archive.md
03-trace-of-jeon-seoyul.md
```

---

## 3. 전체 ZIP으로 스토리 분석을 요청하는 방법

1. `story/_INBOX/`에 기존 소설 원문을 넣습니다.
2. 캐릭터 이미지는 `archive/characters/<character-id>/images/`에 넣습니다.
3. 세계관 메모는 `archive/world/`에 넣습니다.
4. 저장소 전체를 ZIP으로 압축합니다.
5. ZIP을 업로드하고 다음처럼 요청합니다.

```text
이 ZIP 전체를 읽고,
1. 소설 원문 구조 분석
2. 인물/세력/연표 추출
3. 설정 충돌 및 미회수 복선 점검
4. 게임 챕터와 장면 단위로 재구성
5. 모바일 웹 게임 데이터와 화면에 반영
6. 수정된 최신 전체 ZIP 생성
```

분석 후 반영 위치:

```text
story/_INBOX/                     원본 보존
story/prologue, part-*/           정리된 소설
archive/characters/               인물 설정집
archive/world/                    세계관·세력·연표
archive/records/                  극중 기록과 금서
archive/foreshadow/               복선 추적
game/data/stories/                게임 실행용 장면 데이터
game/assets/images/characters/    게임용 최적화 이미지
```

### 원본 보존 원칙

- `_INBOX`의 원본은 삭제하거나 덮어쓰지 않습니다.
- 분석·정리본은 별도 파일로 생성합니다.
- 원문 수정이 필요한 경우 변경 이유를 `story/revisions/`에 기록합니다.
- 설정과 본문이 충돌하면 임의로 단정하지 않고 충돌 목록을 작성합니다.

---

## 4. 디렉터리 구조

```text
Cheonryugwan-Archive/
├── README.md
├── CHANGELOG.md
├── LICENSE
├── PROJECT_RULES.md
├── archive/
│   ├── world/
│   ├── characters/
│   ├── records/
│   ├── foreshadow/
│   ├── endings/
│   └── glossary/
├── story/
│   ├── _INBOX/
│   ├── prologue/
│   ├── part-01/
│   ├── part-02/
│   ├── part-03/
│   ├── part-04/
│   ├── side-stories/
│   ├── drafts/
│   └── revisions/
├── game/
│   ├── index.html
│   ├── manifest.webmanifest
│   ├── service-worker.js
│   ├── assets/
│   └── data/
├── docs/
├── templates/
└── tools/
```

---

## 5. 캐릭터 설정집과 이미지 추가

```text
archive/characters/seo-harin/
├── README.md
├── profile.md
├── personality.md
├── history.md
├── relationships.md
├── abilities.md
├── secrets.md
└── images/
    ├── profile.webp
    ├── full-body.webp
    ├── concept-sheet.webp
    └── expressions/
```

게임 배포용 최적화본은 아래에 둡니다.

```text
game/assets/images/characters/<character-id>/
```

`archive/characters/`에는 원본 설정 자료를, `game/assets/`에는 실제 배포용 파일을 둡니다.

---

## 6. 소설 작성 형식

```markdown
# 제1장 — 읽히지 않은 기록

## 메타데이터
- 시점:
- 시간:
- 장소:
- 등장인물:
- 관련 기록:
- 관련 복선:
- 상태: 초안 / 검토 / 확정

## 본문

기록실은 밤이 깊을수록 더 오래된 냄새를 품었다.

## 장면 메모
- 배경:
- BGM:
- 게임 전환 후보:
```

본문에 게임 명령어를 강제로 섞지 않습니다. 게임화 메모는 `장면 메모` 또는 별도 분석 문서에서 관리합니다.

---

## 7. 게임 반영 과정

```text
Chapter
 ├── Scene
 │    ├── Narration
 │    ├── Dialogue
 │    ├── Background
 │    ├── Character
 │    ├── Music/SFX
 │    ├── Choice
 │    └── State Change
 └── Unlock
      ├── Record
      ├── Character Entry
      └── Foreshadow Update
```

게임 데이터는 `game/data/stories/*.json`에 생성합니다.

---

## 8. 로컬 실행

프로젝트 루트에서:

```bash
python -m http.server 8000
```

접속:

```text
http://localhost:8000/game/
```

---

## 9. GitHub Pages 배포

```text
https://<github-id>.github.io/Cheonryugwan-Archive/game/
```

초기에는 순수 HTML/CSS/JavaScript 구조라 별도 빌드가 필요 없습니다.

---

## 10. 현재 개발 체크리스트

### v0.1.0 — Archive Foundation

- [x] Archive First 구조 정의
- [x] 소설 업로드용 `story/_INBOX/` 생성
- [x] 파트별 소설 폴더 생성
- [x] 세계관·캐릭터·기록·복선 폴더 생성
- [x] 캐릭터 이미지 관리 구조 생성
- [x] 상세 README 작성
- [x] 작성 템플릿 제공
- [x] 모바일 게임 기본 화면 제공
- [x] JSON 샘플 스토리 제공
- [x] PWA 기본 파일 제공
- [ ] 실제 사용자 원문 분석
- [ ] 실제 캐릭터 이미지 연결
- [ ] 본편 장면 데이터 변환
- [ ] 선택지/분기 확장
- [ ] 기록실·인물도감 완성

---

## 11. 버전 운영 방식

```text
v0.1.x  Archive 구조와 작성 표준
v0.2.x  실제 소설 원문 분석 및 정리
v0.3.x  장면 변환과 대화 엔진
v0.4.x  선택지·분기·상태 관리
v0.5.x  기록실·인물도감
v0.6.x  캐릭터 이미지·음향
v0.7.x  PWA·오프라인·모바일 최적화
v1.0.0  공개 가능한 첫 플레이 데모
```

모든 버전은 실행 가능한 최신 ZIP 하나로 관리합니다.

# License

Source Code

- MIT License

Creative Contents

- All Rights Reserved

The story, characters, world settings, illustrations,
records, lore, and other creative assets
are not licensed under the MIT License.

See COPYRIGHT.md for details.