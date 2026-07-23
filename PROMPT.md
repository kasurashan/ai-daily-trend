# AI / Deep Learning Daily Briefing Prompt

매일 AI 및 딥러닝 커뮤니티에서 실제로 주목할 만한 소식을 골라 한국어 브리핑을 작성한다. 최신 소식을 많이 나열하지 말고, 연구자와 실무자가 무엇에 주목하고 논쟁하는지 큐레이션한다.

## 실행 설정

- 실행 주기: 매일
- 실행 시각: `13:30`
- 시간대: `Asia/Seoul`
- GitHub repository: `kasurashan/ai-daily-trend`
- 기본 branch: `main`
- Slack workspace: `AIM-BRIDGE`
- Slack channel: `#ai-trend`
- Slack channel ID: `C07BV673Z53`
- 게시 방식: GitHub 기록, commit, push가 성공하면 Slack에 자동 게시
- 실패 알림: GitHub issue 생성

## 조사 범위

- arXiv 화제 논문: `cs.LG`, `cs.CL`, `cs.CV`, `stat.ML`
- Hugging Face trending 모델/데이터셋
- GitHub trending ML repository
- Hacker News, Reddit `r/MachineLearning`, `r/LocalLLaMA`에서 화제가 된 글
- 주요 랩 블로그 및 release: OpenAI, Anthropic, Google DeepMind, Meta, Mistral, Qwen, Hugging Face, NVIDIA, PyTorch, vLLM 등
- X AI 커뮤니티에서 공개적으로 접근 가능한 스레드, 논쟁, 실험 결과
- 신뢰할 수 있는 출처를 우선 사용한다. X나 커뮤니티 글 하나만으로 기술적 주장을 확정하지 않는다.

## 구성

총 3~4개 아이템을 기본으로 한다. 강한 소식이 부족하면 1~2개만 게시해도 된다. 약한 항목으로 수를 억지로 채우지 않는다.

1. 헤드라인: 큰 소식. 단, 마케팅 hype는 걷어내고 기술적으로 실제로 무엇이 새로운지 중심으로 쓴다.
2. 너드 픽: 대중은 모르지만 커뮤니티에서 화제인 것. 예: star 수가 폭증한 repo, 논쟁 중인 논문, 기발한 benchmark/ablation, 바로 써먹을 수 있는 library나 기법, reproduction 실패 논란.
3. 원 모어 씽: 0~1개. 웃기거나 기발하거나 마이너하지만 알아두면 좋은 것.

## 작성 원칙

- 한국어로 작성하되 `attention`, `distillation`, `fine-tuning`, `inference`, `benchmark`, `ablation`, `checkpoint`, `throughput`, `latency` 같은 통용 기술 용어는 영어로 둔다.
- 각 아이템은 핵심 메시지와 독자가 얻어가야 할 판단을 놓치지 않는다.
- 너무 디테일하지 않아도 된다. high-level이어도 실제 새로움과 의미가 분명하면 충분하다.
- 각 아이템에는 실제 새로움을 보여주는 기술 포인트를 최소 하나 포함한다. 예: architecture, training method, benchmark 조건, 공개 weight, API 동작 변화, 비용, 속도, memory, latency.
- 관련 없는 숫자, 전체 benchmark 표, 세부 implementation 나열은 Slack에 넣지 않는다. 필요하면 GitHub 기록에만 남긴다.
- `author-reported`, 독립 검증 전, benchmark 조건 불일치, reproduction 논란처럼 판단에 영향을 주는 한계는 짧게 표시한다.
- 투자, 인사, 일반 사업 제휴, 마케팅 문구는 기술적 함의가 분명하지 않으면 제외한다.

## GitHub 기록

매 실행 후 다음을 갱신한다.

- `briefings/YYYY/MM/YYYY-MM-DD.md`: 상세 기록
- `data/topics.jsonl`: 중복 방지용 topic 기록
- `latest.md`: 최신 브리핑 요약

조사 시작 전 `data/topics.jsonl`, 최근 30일 기록, `latest.md`를 가볍게 확인한다. 같은 주제는 새 정보가 있을 때만 다시 다룬다.

일일 기록에는 다음만 남기면 된다.

- 오늘의 핵심 3줄
- Slack 게시 항목
- 제외한 주요 후보와 이유
- 계속 추적할 항목

## Slack 형식

Slack 메시지는 1,000~1,800자 정도로 짧게 쓴다. 최대 2,400자를 넘기지 않는다.

```text
*AI / Deep Learning Briefing — YYYY-MM-DD*

■ *오늘의 핵심 3줄*

1. *가장 큰 변화:* ...
2. *실무 영향:* ...
3. *주의할 점:* ...

■ *헤드라인*

1. *정확한 이름이 들어간 제목*

- *핵심:* 한 문장
- *기술 포인트:* 한 문장
- *Takeaway:* 한 문장
- *주의:* 필요한 경우에만 한 문장
- *출처:* <URL|원문>

■ *너드 픽*

2. *정확한 이름이 들어간 제목*

- *핵심:* 한 문장
- *기술 포인트:* 한 문장
- *Takeaway:* 한 문장
- *출처:* <URL|원문>

■ *원 모어 씽*

3. *정확한 이름이 들어간 제목*

- *핵심:* 한 문장
- *Takeaway:* 한 문장
- *출처:* <URL|원문>

---

*상세 기록:* <GitHub Markdown URL|YYYY-MM-DD 리서치 로그>
```

섹션에 넣을 항목이 없으면 해당 섹션은 생략한다.

## 실행 순서

1. 기존 기록을 가볍게 확인한다.
2. 최신 후보를 조사한다.
3. 1~4개 핵심 아이템을 고른다.
4. GitHub 기록 파일을 작성하고 `topics.jsonl`, `latest.md`를 갱신한다.
5. `briefing: add YYYY-MM-DD AI digest`로 commit하고 `main`에 push한다.
6. push가 성공하면 Slack에 게시한다.

GitHub 기록 또는 push에 실패하면 Slack에 게시하지 않는다. 실패 단계와 Slack 미게시 이유를 GitHub issue로 남긴다.

API key, Slack token, GitHub token 등 secret은 파일, commit, issue, 로그에 기록하지 않는다.
