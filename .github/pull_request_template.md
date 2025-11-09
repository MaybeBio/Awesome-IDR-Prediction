# Pull Request Template: Add / Update IDR Prediction Tool or Lab

Thank you for contributing! Please fill out all applicable sections. Incomplete PRs may be requested to revise before review.

## PR Type
- [ ] New tool entry
- [ ] New lab entry
- [ ] Update existing tool/lab info
- [ ] Fix links / formatting
- [ ] Other (describe):

## Tool / Lab Name
Name:

## Summary of Change
Brief rationale (why this is needed):

## Entry Template (Paste Adapted Block Here)
```
### Region
#### Country
##### Institution
<details>
<summary>PI name</summary>

- Lab website: [PI lab](url link) | [PI profile](url link)

- Tools
  - toolname
    - Paper: [paper title](url) (Journal-⚠️is needed if it is a preprint, Year)
    - Abstract: One–three sentence summary (long version placed in docs/<surname>-lab.md)
    - Model/Method: Short computational summary (full version in docs/<surname>-lab.md)
    - Access:
      - Web server: N/A
      - REST API: N/A | [API docs](url)-if it exists
      - Docker image: N/A
      - GitHub repository: N/A
      - Others: package / bio.tools / dataset links
</details>
```

## Checklist
- [ ] Added short Abstract + Method lines only to `README.md`
- [ ] Placed long abstract/method in `docs/<surname>-lab.md` with headings `ToolName Abstract` / `ToolName Model/Method`
- [ ] Anchors follow pattern `#toolname-abstract` / `#toolname-modelmethod`
- [ ] At least one Access item present (Web, GitHub, Docker, API docs, bio.tools, package)
- [ ] No proprietary or confidential data included
- [ ] Links tested (HTTP 200 or reachable)
- [ ] Note added for unpublished tools (⚠️ preprint or experimental)

## Additional Notes for Reviewers
(Anything special, dataset sources, licensing caveats, etc.)

---
Guidelines summary:
- Long content lives in `docs/` aggregated lab file.
- README stays concise: Paper line + short Abstract/Method lines with Read more links.
- Prefer consistent casing for anchors (GitHub auto lowers headings).
- Use hyphens for multi-word tool names in anchors.

Thanks again for making the IDR prediction resource better! ✨
