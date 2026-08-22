# beplepay-developer

Vercel 호스팅 레포 (Vercel 프로젝트명: `we-adp-developer-beple`)

배포 주소: https://we-adp-developer-beple.vercel.app

## 구조

```
index.html              최신 버전으로 보내는 리다이렉트 스텁 (문서 아님)
docs/
  v1.0.0/               버전별 폴더 — 배포 후에도 영구 보존
  v1.0.1/
  v1.0.2/
  v1.0.3/               ← 현재 최신
```

각 버전 폴더에는 원본 파일명의 HTML과, 짧은 URL(`/docs/vX.Y.Z/`)용
리다이렉트 스텁 `index.html`이 함께 들어갑니다.

## URL

기준 도메인: `https://we-adp-developer-beple.vercel.app`

| 경로 | 내용 |
|---|---|
| `/` | 최신 버전으로 자동 이동 |
| `/docs/v1.0.3/` | v1.0.3 (짧은 URL) |
| `/docs/v1.0.3/WE-ADP%20for%20BEPLE%20Developer_v1.0.3.html` | v1.0.3 정식 경로 |

## 새 버전 추가 절차

1. `docs/vX.Y.Z/` 폴더 생성 후 HTML 복사
2. 같은 폴더에 `index.html` 스텁 생성 (기존 버전 것 복사 후 버전 숫자만 교체)
3. 루트 `index.html`의 리다이렉트 대상을 새 버전으로 수정
4. commit & push → Vercel이 자동 재배포

## 주의

Vercel은 레포의 모든 파일을 정적 호스팅합니다.
공개되면 안 되는 파일(pptx, sql, csv, 내부 문서 등)은 레포에 두지 마세요.
