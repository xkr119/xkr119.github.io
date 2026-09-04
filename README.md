# xkr119.github.io

앱 개인정보처리방침과 `app-ads.txt`를 띄우는 **공개 저장소**다.
앱 소스는 각자 비공개 저장소에 있고, 여기에는 웹에 공개해도 되는 것만 둔다.

## 왜 저장소를 따로 두는가

원래 방침은 `capydoku` 저장소의 `docs/`에서 GitHub Pages로 띄웠다.
그런데 **저장소를 비공개로 바꾸는 순간 Pages가 내려가** 방침 URL이 404가 됐다
(2026-09-04에 발견). 무료 플랜은 비공개 저장소에 Pages를 못 띄운다.

방침 페이지는 앱 코드와 생애주기가 다르다 — 코드는 비공개로 두고 싶고
방침은 반드시 공개여야 한다. 그래서 **공개 저장소를 하나만 두고 모든 앱의
방침을 여기서 처리한다.**

`xkr119.github.io`라는 이름이 중요하다. 이 이름이어야 사용자 사이트가 되어
**도메인 루트**(`https://xkr119.github.io/`)를 가져가고, 그래야
`app-ads.txt`를 루트에 놓을 수 있다.

## 주소가 그대로인 이유

Play 콘솔에 넣은 주소는 원래 프로젝트 저장소의 Pages 주소였다:

| 앱 | 콘솔에 들어간 주소 |
|---|---|
| 카피도쿠 | `https://xkr119.github.io/capydoku/` |
| 자개마당 | `https://xkr119.github.io/capydoku/jagaemadang/privacy.html` |

사용자 사이트가 루트를 가져가므로, 이 저장소 안에 `capydoku/` 폴더를 두면
**같은 주소가 그대로 살아난다.** 그래서 콘솔은 손대지 않았다.

> ⚠️ **`capydoku` 저장소의 Pages를 다시 켜지 말 것.** 프로젝트 Pages가
> `/capydoku/` 경로를 가로채서 이 저장소의 파일이 안 보이게 된다.

새 앱은 `/<앱>/privacy.html` 형태로 깔끔한 경로를 쓴다.
`capydoku/onlyonephoto/privacy.html`은 예전 주소 호환용 리다이렉트다.

## 구조

```
index.html                            방침 목록 (개발자 웹사이트로 쓸 수 있다)
app-ads.txt                           AdMob 퍼블리셔 선언 — 루트에 있어야 한다
capydoku/index.html                   카피도쿠 (ko/en 한 페이지)
capydoku/jagaemadang/privacy.html     자개마당
capydoku/onlyonephoto/privacy.html    → /onlyonephoto/ 로 리다이렉트
onlyonephoto/privacy.html             한장만
```

## app-ads.txt

```
google.com, pub-6397306281388525, DIRECT, f08c47fec0942fa0
```

퍼블리셔 한 줄이면 **그 AdMob 계정의 모든 앱이 검증된다** — 앱마다 줄을
추가하지 않는다. 마지막 값은 구글의 인증 ID로 고정이다.

AdMob이 이 파일을 찾아오려면 Play 콘솔 등록정보의 **웹사이트** 항목이
이 도메인이어야 한다. 크롤링은 며칠 걸리고, 없어도 광고는 나온다.

## 고칠 때

방침 원본은 각 앱 저장소의 `store/privacy.md`에 있다. 문안을 고치면
그쪽과 여기를 **함께** 고치고, 페이지의 최종 수정일도 바꾼다.
