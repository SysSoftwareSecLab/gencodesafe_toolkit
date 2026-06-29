```
gencodesafe_toolkit/
  README.md
  LICENSE
  CITATION.cff
  CONTRIBUTING.md
  SECURITY.md
  MANIFEST.md
  pyproject.toml
  src/gencodesafe/
    analyzer.py
    rules.py
    quality.py
    performance.py
    hallucination.py
    api_knowledge.py
    compare.py
    reporting.py
    cli.py
  examples/
    python/
    java/
    javascript/
  docs/
    DESIGN.md
    USAGE.md
    RULES.md
    REPORT_FORMAT.md
    REPAIR_VALIDATION.md
    FDCT_REPORT_MAPPING.md
    GITHUB_RELEASE_CHECKLIST.md
  tests/
  reports/
  scripts/run_demo.sh
```
RUN
```
cd gencodesafe_toolkit
python -m pip install -e .

gencodesafe analyze examples/python/insecure_llm_output.py --format md
gencodesafe batch examples --format md --out reports/demo_report.md
gencodesafe compare examples/python/insecure_llm_output.py examples/python/revised_still_risky.py --format md
gencodesafe validate examples
python -m unittest discover -s tests
```

核心功能包括：

生成式代碼質量評估
安全風險檢測
性能問題提示
可疑 API / 幻覺式接口風險檢測
優化建議與 Markdown/JSON 報告輸出
原始代碼與修復後代碼比較
Pseudo-Repair / Vulnerability Mutation / Regression 風險提示
Python / Java / JavaScript / C/C++ 的輕量規則支持
GitHub 開源所需 README、LICENSE、CITATION、SECURITY、CONTRIBUTING 和 release checklist

TRL5中期原型/開源前工程基礎版本，後續可再擴展 CI/CD、更多語言規則、更完整 benchmark、用戶試用記錄和 Web/API 平台。
