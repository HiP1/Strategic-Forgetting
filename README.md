# Strategic Forgetting

**Ephemeral Retrieval and Tiered Context Persistence for LLM Inference**

HiP (Ivan Phan) · [ORCID: 0009-0003-1095-5855](https://orcid.org/0009-0003-1095-5855)

Concept Note · March 2026 · doi:[10.5281/zenodo.19200814](https://doi.org/10.5281/zenodo.19200814)

---

## Summary

Tool-augmented LLM sessions accumulate retrieved content (search results, API responses, document extracts) that does not just waste context capacity — it actively degrades the model's ability to attend to the content that matters. The "lost in the middle" phenomenon and context rot research demonstrate that model performance worsens as input length increases, even before the window fills. Current platforms retain everything until overflow, then discard silently.

This concept note proposes a tiered retention architecture with three modes (full, summary, ephemeral), four recoverability classes, and a retention note schema that makes every compression decision inspectable by the user. The user can see what is retained, pin content that matters, set priority, and trigger re-retrieval of anything that was flushed.

The security analysis identifies semantic cache poisoning as a specific risk when summarisation is performed on untrusted content, drawing on cross-model empirical findings from [The Confidence Curriculum](https://doi.org/10.5281/zenodo.19199055) series (Phan, 2026). The proposal's core value does not depend on summarisation being secure: even without it, the metadata layer (turn numbers, content types, source pointers) provides inspectability that does not exist today.

The paper specifies the retention contract (invariants, schema, recoverability constraints). It does not prescribe a single default policy. Calibrating defaults by content type, task type, domain, and user profile is a platform-level product decision and a natural site of competitive differentiation.

## Files

| File | Description |
|------|-------------|
| `strategic-forgetting-final.pdf` | Paginated PDF (25 pages, TeX Gyre Heros) |
| `strategic-forgetting.html` | Continuous-scroll HTML with floating TOC and embedded figures |
| `strategic-forgetting-final.md` | Canonical markdown source |

The PDF and HTML are both suitable for reading. The PDF is the archival format for citation tools and indexers. The HTML is the better reading experience for practitioners.

## How to cite

See [CITATION.cff](CITATION.cff) for machine-readable citation metadata, or use:

> Phan, I. (2026). Strategic Forgetting: Ephemeral Retrieval and Tiered Context Persistence for LLM Inference. Concept note. doi:10.5281/zenodo.19200814.

BibTeX:

```bibtex
@misc{phan2026strategicforgetting,
  author       = {Phan, Ivan},
  title        = {Strategic Forgetting: Ephemeral Retrieval and Tiered Context Persistence for {LLM} Inference},
  year         = {2026},
  month        = {3},
  doi          = {10.5281/zenodo.19200814},
  url          = {https://doi.org/10.5281/zenodo.19200814},
  note         = {Concept note}
}
```

## Related work

This paper cites [The Confidence Vulnerability](https://doi.org/10.5281/zenodo.19199055) (Paper 1 of The Confidence Curriculum series) for empirical evidence on summariser vulnerability to indirect prompt injection.

The paper is independent of The Confidence Curriculum series but shares an author.

## Methodology

Developed through adversarial multi-model collaboration: Claude (Weaver/generative collaborator), ChatGPT (Surgeon/structural critique), Gemini (Alchemist/mechanism critique), with HiP as sole editorial authority.

## Licence

This work is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). See [LICENCE](LICENCE) for details.
