# Tech Spec Lite Template

**Version**: 1.0  
**Purpose**: Lightweight technical specification for Quick Track projects  
**Location**: `.sdlc/primitives/templates/quick-track/tech-spec-lite_template.md`

---

## When to Use

Use this template for:
- Bug fixes
- Small features (< 2 weeks effort)
- Well-understood changes with clear requirements
- Projects following the **Quick Track** methodology

For larger or more complex projects, use the full `spec_template.md` instead.

---

## Template

```markdown
# Tech Spec: [Title]

**Date**: [YYYY-MM-DD]  
**Author**: [Name]  
**Status**: [Draft | Review | Approved]  
**Track**: Quick

---

## Problem Summary

[2-3 sentences describing what problem this solves. Be specific.]

**Example**:
> Users are unable to export reports to PDF format. They currently have to 
> screenshot each page manually, which takes 10+ minutes for large reports.
> This feature adds a one-click PDF export.

---

## Proposed Solution

[Bullet points describing what we're building]

- [Core functionality point 1]
- [Core functionality point 2]
- [Core functionality point 3]

**Out of Scope**:
- [What we're explicitly NOT doing]
- [Another exclusion]

---

## Implementation Approach

### Technical Approach

[How we'll build this - key technical decisions]

1. [Step/Approach 1]
2. [Step/Approach 2]
3. [Step/Approach 3]

### Key Decisions

| Decision | Choice | Rationale |
|----------|--------|-----------|
| [Decision point] | [What we chose] | [Why] |

---

## Files/Components Affected

| File/Component | Change Type | Description |
|----------------|-------------|-------------|
| [path/file.ext] | [New/Modify/Delete] | [Brief description] |
| [path/file.ext] | [New/Modify/Delete] | [Brief description] |

---

## Testing Approach

### Manual Testing
- [ ] [Test scenario 1]
- [ ] [Test scenario 2]

### Automated Testing
- [ ] [Unit test for X]
- [ ] [Integration test for Y]

### Edge Cases
- [ ] [Edge case to verify]
- [ ] [Another edge case]

---

## Risks & Concerns

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| [Risk description] | [Low/Med/High] | [Low/Med/High] | [How to mitigate] |

[If no significant risks, state: "No significant risks identified for this change."]

---

## Rollback Plan

[For production changes - how to roll back if needed]

- [ ] [Rollback step 1]
- [ ] [Rollback step 2]

[If N/A, state: "Standard deployment rollback - revert to previous version."]

---

## Estimated Effort

| Task | Estimate |
|------|----------|
| Implementation | [X hours/days] |
| Testing | [X hours/days] |
| Code Review | [X hours] |
| **Total** | **[X hours/days]** |

---

## Approval

| Role | Name | Date | Status |
|------|------|------|--------|
| Tech Lead | [Name] | [Date] | [Pending/Approved] |

---

## Notes

[Any additional context, links to related tickets, or other relevant information]
```

---

## Completion Checklist

Before submitting for review, ensure:

- [ ] Problem summary is clear and specific
- [ ] Solution is described in concrete terms
- [ ] Files/components affected are listed
- [ ] Testing approach covers happy path and key edge cases
- [ ] Risks are identified (or explicitly stated as none)
- [ ] Estimate is realistic
- [ ] No unexplained technical decisions

---

## Example: Completed Tech Spec Lite

```markdown
# Tech Spec: Add PDF Export to Reports

**Date**: 2025-12-13  
**Author**: Jane Developer  
**Status**: Approved  
**Track**: Quick

---

## Problem Summary

Users are unable to export reports to PDF format. They currently have to 
screenshot each page manually, which takes 10+ minutes for large reports 
and loses formatting. This feature adds a one-click PDF export that maintains 
report styling.

---

## Proposed Solution

- Add "Export to PDF" button to report toolbar
- Generate PDF client-side using existing report HTML
- Maintain current report styling (headers, tables, charts)
- Support reports up to 50 pages

**Out of Scope**:
- Server-side PDF generation
- Custom PDF styling options
- Batch export of multiple reports

---

## Implementation Approach

### Technical Approach

1. Add jsPDF library (v2.5.1) for client-side PDF generation
2. Create PDFExporter service class to handle conversion
3. Add export button to ReportToolbar component
4. Use html2canvas for chart/image capture

### Key Decisions

| Decision | Choice | Rationale |
|----------|--------|-----------|
| PDF Library | jsPDF | Mature, well-documented, no server dependency |
| Chart Handling | html2canvas | Preserves chart appearance exactly |
| Page Breaking | Auto | Let library handle, manual breaks add complexity |

---

## Files/Components Affected

| File/Component | Change Type | Description |
|----------------|-------------|-------------|
| package.json | Modify | Add jsPDF, html2canvas deps |
| src/services/PDFExporter.ts | New | PDF generation service |
| src/components/ReportToolbar.tsx | Modify | Add export button |
| src/styles/print.css | Modify | PDF-specific styles |

---

## Testing Approach

### Manual Testing
- [ ] Export single-page report
- [ ] Export multi-page report (10+ pages)
- [ ] Verify tables render correctly
- [ ] Verify charts render correctly
- [ ] Test on Chrome, Firefox, Safari

### Automated Testing
- [ ] Unit test PDFExporter.generatePDF()
- [ ] Unit test page break calculation
- [ ] Component test export button click handler

### Edge Cases
- [ ] Empty report (no data)
- [ ] Report with 50+ pages (performance)
- [ ] Report with special characters in title

---

## Risks & Concerns

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| Large reports slow/crash browser | Medium | Medium | Add progress indicator, test with max size |
| Chart rendering inconsistency | Low | Low | Use html2canvas with retina settings |

---

## Rollback Plan

Standard deployment rollback - revert to previous version. No data 
migration or external dependencies affected.

---

## Estimated Effort

| Task | Estimate |
|------|----------|
| Implementation | 6 hours |
| Testing | 2 hours |
| Code Review | 1 hour |
| **Total** | **9 hours (~1.5 days)** |

---

## Approval

| Role | Name | Date | Status |
|------|------|------|--------|
| Tech Lead | Bob Lead | 2025-12-13 | Approved |

---

## Notes

- Related ticket: JIRA-1234
- Similar implementation in mobile app: see `mobile/src/export/`
- User research showing PDF is most requested export format
```

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-12-13 | Initial version |
