# xkr119.github.io

앱 방침 페이지의 **입구**이자 `app-ads.txt`가 사는 곳이다.
사용자 사이트라 도메인 루트(`https://xkr119.github.io/`)를 가져간다.

## 방침은 앱마다 어디에 있는가

**소스는 비공개, 방침은 공개** — 앱마다 공개 저장소를 하나씩 둔 방식이
이미 있었다. 여기는 그걸 대체하는 게 아니라 루트를 채우고 목록을 준다.

| 앱 | 소스 (비공개) | 방침 페이지 | 주소 |
|---|---|---|---|
| 카피도쿠 | `capydoku` | **이 저장소** `capydoku/` | `/capydoku/` |
| 자개마당 | `jagaemadang` | **이 저장소** `capydoku/jagaemadang/` | `/capydoku/jagaemadang/privacy.html` |
| 한장만 | `onlyonephoto` | `onlyonephoto-privacy` | `/onlyonephoto-privacy/` |
| 냥캐슬 디펜스 | `idle-defense` | `idle-defense-dist` | `/idle-defense-dist/privacy.html` |

카피도쿠·자개마당만 여기 있는 이유: 두 앱은 방침을 `capydoku` 저장소의
`docs/`에서 띄우고 있었는데, **그 저장소를 비공개로 바꾼 순간 Pages가
내려가 방침 URL이 404가 됐다**(2026-09-04에 발견). 무료 플랜은 비공개
저장소에 Pages를 못 띄운다.

새로 공개 저장소를 두 개 더 만드는 대신, 루트를 쥔 이 저장소에 담았다.
`app-ads.txt`도 루트에 있어야 해서 어차피 필요한 저장소였다.

## 주소를 안 바꾼 이유

Play 콘솔에 이미 들어간 주소가 `xkr119.github.io/capydoku/...`였다.
사용자 사이트가 루트를 가져가므로 이 저장소에 `capydoku/` 폴더를 두면
**같은 주소가 그대로 살아난다.** 그래서 콘솔은 손대지 않았다.

> ⚠️ **`capydoku` 저장소의 Pages를 다시 켜지 말 것.** 프로젝트 Pages가
> `/capydoku/` 경로를 가로채서 이 저장소의 파일이 안 보이게 된다.

## 구조

```
index.html                            방침 목록 (개발자 웹사이트 칸에 넣는 주소)
app-ads.txt                           AdMob 퍼블리셔 선언 — 루트에 있어야 한다
capydoku/index.html                   카피도쿠 (ko/en 한 페이지)
capydoku/jagaemadang/privacy.html     자개마당
onlyonephoto/privacy.html             → /onlyonephoto-privacy/ 로 리다이렉트
capydoku/onlyonephoto/privacy.html    → 같은 곳으로 리다이렉트
```

리다이렉트 두 개는 한장만 방침을 잠깐 이 저장소에도 복사했다가 정본이
`onlyonephoto-privacy`임을 확인하고 남겨둔 것이다. **방침 본문을 두 곳에
두면 반드시 갈라진다** — 그래서 사본을 지우고 리다이렉트만 남겼다.

## app-ads.txt

```
google.com, pub-6397306281388525, DIRECT, f08c47fec0942fa0
```

퍼블리셔 한 줄이면 **그 AdMob 계정의 모든 앱이 검증된다** — 앱마다 줄을
추가하지 않는다. 마지막 값은 구글의 인증 ID로 고정이다.

AdMob이 이 파일을 찾아오려면 Play 콘솔 등록정보의 **웹사이트** 항목이
`https://xkr119.github.io`여야 한다. 크롤링은 며칠 걸리고, 없어도 광고는 나온다.

## 고칠 때

방침 원본은 각 앱 저장소의 `store/privacy.md`에 있다. 문안을 고치면
그쪽과 페이지를 **함께** 고치고 최종 수정일도 바꾼다.
