# Graph Report - msds-ozetleyici  (2026-11-16)

## Corpus Check
- 8 files · ~31,903 words
- Verdict: corpus is large enough that graph structure adds value.
- Unclassified: 1 file(s) not represented in the graph (top: (none) 1)

## Summary
- 176 nodes · 313 edges · 12 communities (9 shown, 3 thin omitted)
- Extraction: 99% EXTRACTED · 1% INFERRED · 0% AMBIGUOUS · INFERRED: 2 edges (avg confidence: 0.9)
- Token cost: 0 input · 0 output

## Graph Freshness
- Built from commit: `1a5af552`
- Run `git rev-parse HEAD` and compare to check if the graph is stale.
- Run `graphify update .` after code changes (no API cost).

## Community Hubs (Navigation)
- call_openai_compatible
- msds_ozetleyici.py
- main
- call_ai
- generate_html_card
- re
- ai_cache.py
- build_excel_summary
- adr_tablodan_tamamla
- _muhtemelen_turkce_degil

## God Nodes (most connected - your core abstractions)
1. `main()` - 23 edges
2. `generate_html_card()` - 15 edges
3. `analyze_rule_based()` - 13 edges
4. `call_openai_compatible()` - 13 edges
5. `_call_single_model()` - 11 edges
6. `call_ai()` - 11 edges
7. `_satir_degeri()` - 9 edges
8. `sonucu_turkceye_cevir()` - 9 edges
9. `json_ayikla()` - 9 edges
10. `cached_call()` - 8 edges

## Surprising Connections (you probably didn't know these)
- `Adım 2 — Streamlit Cloud'da Yayınla` --references--> `main()`  [INFERRED]
  YAYINLAMA_KILAVUZU.md → msds_ozetleyici.py

## Import Cycles
- None detected.

## Communities (12 total, 3 thin omitted)

### Community 0 - "call_openai_compatible"
Cohesion: 0.10
Nodes (15): call_claude(), call_gemini(), call_groq(), call_nvidia_nim(), call_ollama(), call_openai_compatible(), _build_payload(), call_openrouter() (+7 more)

### Community 1 - "msds_ozetleyici.py"
Cohesion: 0.08
Nodes (5): build_combined_html(), _cas_bul(), _cas_check_digit(), _extract_card(), extract_pdf_text()

### Community 2 - "main"
Cohesion: 0.10
Nodes (15): diagnose_error(), html_to_pdf_bytes(), kart_ac_widget(), main(), build_failover_chain(), engine_available(), _show_live(), tds_dosyasi_mi() (+7 more)

### Community 3 - "call_ai"
Cohesion: 0.11
Nodes (12): analyze_with_failover(), _gercek_analiz(), call_ai(), ceviri_prompt_olustur(), _cevrilebilir_alanlari_topla(), gez(), infer_pictograms_from_text(), _is_daily_exhausted_error() (+4 more)

### Community 4 - "generate_html_card"
Cohesion: 0.13
Nodes (14): adr_etiket_elmasi(), _adr_norm_kod(), cikti_adi_olustur(), fab(), flatten_text(), generate_html_card(), kr(), make_diamond() (+6 more)

### Community 5 - "re"
Cohesion: 0.15
Nodes (9): analyze_rule_based(), _kod_ifadeleri(), _yollar(), _blok_ozeti(), _bolum1_alan_kes(), _bolumlere_ayir(), _satir_degeri(), _temiz() (+1 more)

### Community 6 - "ai_cache.py"
Cohesion: 0.14
Nodes (5): _cache_path(), cache_stats(), cached_call(), clear_cache(), _hash_of()

### Community 7 - "build_excel_summary"
Cohesion: 0.50
Nodes (3): build_excel_summary(), cell(), join_list()

### Community 9 - "_muhtemelen_turkce_degil"
Cohesion: 0.50
Nodes (3): _metin_parcalarini_topla(), gez(), _muhtemelen_turkce_degil()

## Knowledge Gaps
- **3 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `main()` connect `main` to `call_openai_compatible`, `msds_ozetleyici.py`, `call_ai`, `generate_html_card`, `ai_cache.py`, `build_excel_summary`?**
  _High betweenness centrality (0.135) - this node is a cross-community bridge._
- **Are the 2 inferred relationships involving `main()` (e.g. with `_on_switch()` and `Adım 2 — Streamlit Cloud'da Yayınla`) actually correct?**
  _`main()` has 2 INFERRED edges - model-reasoned connections that need verification._
- **Should `call_openai_compatible` be split into smaller, more focused modules?**
  _Cohesion score 0.09885057471264368 - nodes in this community are weakly interconnected._
- **Should `msds_ozetleyici.py` be split into smaller, more focused modules?**
  _Cohesion score 0.08262108262108261 - nodes in this community are weakly interconnected._
- **Should `main` be split into smaller, more focused modules?**
  _Cohesion score 0.09782608695652174 - nodes in this community are weakly interconnected._
- **Should `call_ai` be split into smaller, more focused modules?**
  _Cohesion score 0.10822510822510822 - nodes in this community are weakly interconnected._
- **Should `generate_html_card` be split into smaller, more focused modules?**
  _Cohesion score 0.12857142857142856 - nodes in this community are weakly interconnected._