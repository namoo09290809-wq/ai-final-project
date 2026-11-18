# 남을 위한 AI — ai-final-project

한 사람을 위한 AI 웹 서비스. `ai-agent-demo` 템플릿 구조를 따르고 화면 디자인만 새로 했다.

- 주소: https://ai-final-project.pages.dev
- 배포: GitHub `main` → Cloudflare Pages (빌드 명령 없음, 출력 디렉터리는 `wrangler.toml` 의 `public`)
- AI: Cloudflare Workers AI 바인딩 `AI` (API 키 없음)

## 고치는 곳

`functions/_config.js` 한 파일. 대상·하는 일·기준 3줄·멈춤·모델·화면 글자.

## 구조

```
public/index.html        화면
functions/_config.js     ← 여기만 고친다
functions/api/ask.js     지시문을 만들어 AI 에 보냄 (답 / 되물음)
functions/api/meta.js    화면 글자를 내보냄
AGENTS.md                사람과 AI가 같이 읽는 설명서
docs/                    인터뷰 기록 · 명세서 · 점검
wrangler.toml            Cloudflare 설정 + AI 바인딩
```

## 확인

1. 정상 입력 → 기준 세 줄을 지킨 답이 나오는가
2. 일부러 정보를 빼고 입력 → 답하지 않고 되묻는가 (파란 「먼저 확인할 것」)

디버그: `/api/ask?debug=1` 로 POST 하면 모델 원문 일부를 함께 돌려준다.
