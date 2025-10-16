# Operations — Launch Checklist & Metrics

## Preflight Checklist
- [ ] Pixel + CAPI verified (Test Events green)
- [ ] UTM schema documented (`utm_source=meta&utm_campaign=quiz_pilot`…)
- [ ] Quiz live + thank-you URL configured
- [ ] 4–5 angles × (video + static) uploaded
- [ ] Campaign objective: **Leads** (optimize for `Lead`)
- [ ] Budget + learning period expectations documented

## Reporting (MVP)
Track daily:
- CPL, Quiz completion %, Book rate %, Show rate %
- Match rate (CAPI), Signal loss warnings, Event diagnostics

## First Optimization Pass (48–72h)
- Pause obvious laggards (CP(L) outliers)
- Keep one winner per angle; test a fresh variation of the winner
- Log decisions in `/logs/` with reasons (not just results)
