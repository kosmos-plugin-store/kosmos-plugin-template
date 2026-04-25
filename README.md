# kosmos-plugin-template

> KOSMOS 플러그인 작성을 위한 GitHub 템플릿 repository.

이 repo 의 "Use this template" 버튼을 눌러 새 플러그인을 시작하세요.
또는 KOSMOS TUI / Python fallback 으로 직접 스캐폴딩 가능합니다:

```sh
# TUI (Bun + Ink)
kosmos plugin init my_plugin --non-interactive --tier live --layer 1 --no-pii

# Python entry-point (uvx)
uvx kosmos-plugin-init my_plugin --tier live --layer 1 --no-pii
```

## 시작하기

1. **Use this template** → 새 repo 생성 (이름: `kosmos-plugin-<your-plugin-id>`).
2. 클론 후 `plugin_my_plugin/` 디렉토리와 `my_plugin` 식별자를 일괄 치환:

```sh
git clone https://github.com/<your-org>/kosmos-plugin-busan_bike
cd kosmos-plugin-busan_bike

git mv plugin_my_plugin plugin_busan_bike
sed -i '' 's/my_plugin/busan_bike/g' \
  manifest.yaml \
  plugin_busan_bike/*.py \
  tests/test_adapter.py \
  pyproject.toml \
  README.ko.md README.en.md
git mv tests/fixtures/plugin.my_plugin.lookup.json \
       tests/fixtures/plugin.busan_bike.lookup.json
```

3. `manifest.yaml` 의 search hint / Layer / PII 필드를 자신의 플러그인에 맞게 편집.
4. `uv sync && uv run pytest` 로 녹색 확인.
5. PR 으로 push.

## 다음 단계

- 가이드: <https://github.com/umyunsang/KOSMOS/blob/main/docs/plugins/quickstart.ko.md>
- 아키텍처: <https://github.com/umyunsang/KOSMOS/blob/main/docs/plugins/architecture.md>
- `data.go.kr` 키 패턴: <https://github.com/umyunsang/KOSMOS/blob/main/docs/plugins/data-go-kr.md>

## 라이선스

Apache-2.0.
