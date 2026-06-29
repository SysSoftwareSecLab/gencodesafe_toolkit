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
