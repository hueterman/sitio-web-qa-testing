# QA Testing Checklist - Sitio Web

## HTML Validation
- [ ] W3C Validator: 0 errors
- [ ] W3C Validator: ≤3 warnings
- [ ] Tool: https://validator.w3.org/
- [ ] Screenshot saved

## Accessibility
- [ ] WAVE audit: 0 errors
- [ ] WAVE audit: ≤5 alerts
- [ ] Color contrast: ≥4.5:1 (body text)
- [ ] Color contrast: ≥4.5:1 (links)
- [ ] Color contrast: ≥4.5:1 (buttons)
- [ ] Focus indicators visible (TAB navigation)
- [ ] Tool: WAVE Chrome Extension
- [ ] Tool: Color Contrast Analyzer

## Responsive Design
- [ ] 320px (iPhone SE): Vertical layout, touch-friendly
- [ ] 768px (iPad): 2-column grid
- [ ] 1024px (Desktop): 3-column grid
- [ ] Max-width respected (≤1200px)
- [ ] No horizontal scrolling
- [ ] Images scale correctly
- [ ] Text readable without zoom
- [ ] Tool: Chrome DevTools Responsive Mode

## Performance
- [ ] Lighthouse Performance: ≥90
- [ ] Lighthouse Accessibility: ≥90
- [ ] Lighthouse Best Practices: ≥90
- [ ] CSS used: >80% (no unused code)
- [ ] Animations: 60 FPS smooth
- [ ] Tool: Chrome DevTools Lighthouse

## Cross-Browser
- [ ] Chrome (latest): ✓
- [ ] Firefox (latest): ✓
- [ ] Safari (latest): ✓
- [ ] Edge (latest): ✓
- [ ] Mobile Safari (iPhone): ✓
- [ ] Chrome Mobile (Android): ✓

## Form Testing
- [ ] Required fields validated
- [ ] Email format validated
- [ ] Character limits respected (maxlength)
- [ ] Buttons touch-friendly (≥48px)
- [ ] Error messages clear
- [ ] Submit works correctly

## Git Workflow
- [ ] Commit messages clear and descriptive
- [ ] PR has detailed description
- [ ] Branch naming follows convention
- [ ] No merge conflicts
- [ ] All tests passing before merge
