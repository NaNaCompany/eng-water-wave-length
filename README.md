# 유한 수심 수면파 파장 계산기

유한 수심의 선형 중력파 분산식을 양의 파수에 대해 풀어 파장을 계산합니다. 얕은 물·깊은 물의 근사 사이도 연속적으로 계산합니다.

- ID: E140
- App: https://nanalab.kr/eng-water-wave-length/
- Repository: https://github.com/NaNaCompany/eng-water-wave-length
- Formula: (2π/T)² = gk tanh(kh), λ = 2π/k

## Model and data

작은 진폭의 선형 중력파이며 바닥은 수평이고 수심이 일정합니다. 비압축성·비점성·비회전 유동이며 평균 흐름이 없습니다. 표면장력·쇄파·강한 비선형성을 무시합니다. 모세관파나 급변 수심에는 적용하지 않습니다.

Inputs normalize to SI. Repeated-input models support adding/removing actual input rows. Calculations, finite-number checks and physical-domain checks run locally; no external property database or solver API is used.

## Validation

Run node --test tests/*.test.mjs and python scripts/build-locales.py --check. tests/reference.json contains independently computed high-precision default and boundary references. The source notices distinguish original MIT work from citation-only external references.

## Static languages

Korean (existing root), English (`en/`), Spanish (`es/`), Simplified Chinese (`zh/`), Japanese (`ja/`) and German (`de/`). Each page has its own canonical URL, reciprocal hreflang, localized metadata, interface, validation messages and preview image. The language links work without JavaScript. Calculation code is shared and no runtime translation API is used.

Edit `localization/*.json` for text, `src/template.html` for the shared page, and run `python scripts/build-locales.py`. Run `python scripts/build-locales.py --check` and `npm test` before publishing. Decimal commas are accepted in Spanish and German; thousands separators are not supported.
