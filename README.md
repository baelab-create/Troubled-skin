# 문제성 피부 4주 로테이션 관리 프로그램

> 숭실대학교 의공학 연구실 · 배원규 교수 연구실 · 에스테틱 전문가 교육용

피부장벽이 손상된 여드름 성향 문제성 피부를 위한, 1~2주 간격 재방문 고객 대상의 4주 로테이션 에스테틱 샵 관리 프로토콜입니다. 본 자료는 화장품 표시·광고법을 준수하여 작성되었으며, 의약품적 효능·효과를 표방하지 않습니다.

---

## 📂 파일 구조

```
.
├── index.html          # 메인 교육자료 (단일 파일, 모든 스타일 포함)
├── assets/
│   └── hero.jpg        # 대표 이미지 · OG 썸네일
└── README.md
```

---

## 🚀 GitHub Pages 배포 가이드

### 1단계 · GitHub 저장소 생성

1. GitHub에서 새 저장소(Repository)를 만듭니다. 저장소명은 예를 들어 `dr-bae-program` 처럼 자유롭게 지정합니다.
2. Public으로 설정합니다 (GitHub Pages 무료 플랜에서는 Public 저장소만 가능).

### 2단계 · 로컬에서 파일 업로드

터미널에서 아래 명령을 순서대로 실행합니다:

```bash
cd dr-bae-program
git init
git add .
git commit -m "Initial commit: Dr. BAE problem skin program"
git branch -M main
git remote add origin https://github.com/baelab-create/Troubled-skin.git
git push -u origin main
```

> GitHub 웹 UI에서 직접 파일을 드래그해서 업로드해도 됩니다. 그 경우 `index.html`과 `assets/hero.jpg`를 루트에 올리면 됩니다.

### 3단계 · GitHub Pages 활성화

1. 저장소 → **Settings** → **Pages** 메뉴로 이동합니다.
2. **Source** 를 `Deploy from a branch` 로 설정합니다.
3. **Branch** 를 `main` / `/ (root)` 로 선택하고 **Save** 를 누릅니다.
4. 1~2분 후 `https://baelab-create.github.io/Troubled-skin/` 에서 접속 가능해집니다.

### 4단계 · 소셜 공유 URL 갱신 (중요)

`index.html`의 `<head>` 상단에 있는 OG/Twitter 메타 태그의 **4개 URL**을 본인의 실제 주소로 바꿔야 카카오톡·슬랙·페이스북·X 등에서 썸네일이 정상 표시됩니다.

**바꿔야 할 값 (index.html 안에서 찾기):**

```
https://baelab-create.github.io/Troubled-skin/          (og:url)
https://baelab-create.github.io/Troubled-skin/assets/hero.jpg   (og:image, og:image:secure_url, twitter:image)
```

**빠르게 일괄 치환하는 방법** (macOS/Linux 터미널):

```bash
sed -i '' 's|baelab-create|실제사용자명|g; s|Troubled-skin|실제저장소명|g' index.html
```

Windows PowerShell:

```powershell
(Get-Content index.html) -replace 'baelab-create', '실제사용자명' -replace 'Troubled-skin', '실제저장소명' | Set-Content index.html
```

치환 후 다시 커밋·푸시합니다:

```bash
git add index.html
git commit -m "Update social sharing URLs"
git push
```

### 5단계 · 썸네일 반영 확인

배포 후 카카오톡·슬랙 등에서 링크를 붙여넣을 때 썸네일이 안 보이면, 각 플랫폼의 캐시 때문일 수 있습니다. 아래 디버거로 강제 갱신할 수 있습니다:

- **카카오톡** — https://developers.kakao.com/tool/debugger/sharing
- **페이스북·Instagram** — https://developers.facebook.com/tools/debug/
- **X(Twitter)** — 카드 갱신은 12~24시간 내 자동 반영
- **슬랙** — 채널에서 메시지 다시 붙여넣기 또는 `/unfurl-toggle-always-on` 사용

---

## 🌐 Custom Domain (선택)

자체 도메인(예: `program.drbae.kr`)을 연결하려면:

1. 저장소 루트에 `CNAME` 파일을 만들고, 파일 내용에 도메인만 한 줄로 입력합니다.
   ```
   program.drbae.kr
   ```
2. 도메인 DNS 설정에서 CNAME 레코드를 `baelab-create.github.io` 로 추가합니다.
3. Settings → Pages에서 Custom Domain 입력 후 Enforce HTTPS를 체크합니다.
4. `index.html`의 OG 메타 태그 URL을 자체 도메인으로 다시 갱신합니다.

---

## 📝 교육자료 구성 (Section Map)

| No. | 섹션 | 내용 |
|-----|------|------|
| 01  | 4주 로테이션 한눈에 보기 | 주차별 테마·주연 제품 매트릭스 |
| 02  | 관리 프로그램 설계 사이언스 | PHA·센텔라 트리플 액티브·칼슘그래디언트·EGF·마이크로바이옴·히알루론산·Tachyphylaxis |
| 03  | 적용 대상의 병태생리 구분 | 여드름(*C. acnes*) vs 말라세지아 계열 감별 체크리스트 |
| 04  | 초회 방문 스크리닝 & 금기 | 절대 금기·상대적 주의·패치 테스트·홈케어 인벤토리 |
| 05  | 주차별 관리 프로그램 | Week 1~4 단계별 프로토콜 |
| 06  | 전성분 기여 매트릭스 | 제품별 전성분 기반 역할 |
| 07  | 부작용 대응 프로토콜 | Immediate/Delayed Decision Tree · 반응 레벨 A~F |
| 08  | 홈케어 연계 가이드 | 리퀴드 마스크 오버나이트 · 토코포르테 미스트 |

---

## ⚖️ 법적·윤리적 고지

- 본 자료는 에스테틱 전문가 교육용 내부 참고자료이며, 대외 광고·마케팅 문구로 직접 전용될 수 없습니다.
- 모든 표현은 **화장품 표시·광고법** 범위 내에서 작성되었으며, "재생·치료·치유·항염" 등 의약품적 표현은 사용하지 않습니다.
- 본 프로토콜은 에스테틱 샵 관리용이며, 의학적 진단·치료를 대체하지 않습니다. 의료적 판단이 필요한 케이스는 **반드시 피부과 전문의 진단**을 우선합니다.

---

## 🏛 저작 표시

**숭실대학교 의공학 연구실** · 배원규 교수 연구실
Soongsil University · Biomedical Engineering Lab · Dr. Won-gyu Bae

Dr. BAE · 2026 Ed.
