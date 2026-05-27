---
name: xinji-pencil-app-style
description: Apply the 心迹档案 / Union Soul Pencil prototype visual system to websites, mobile apps, dashboards, prototype screens, and investor-demo product UIs. Use when designing or redesigning 心迹档案, Union Soul, AI companionship, memory-management, token recharge, prompt-debugging, smart-agent, wearable-ring, privacy/safety, or soft emotional AI product interfaces in a warm ivory, paper-card, pastel Pencil-style app aesthetic.
---

# Xinji Pencil App Style

Use this skill to turn product requirements or existing UI into the 心迹档案 Pencil prototype style: warm ivory canvas, mobile-first app surfaces, editorial Chinese headings, soft paper cards, delicate pink/cyan/lavender accents, calm icon buttons, and product-dense companion AI workflows.

## Workflow

1. Identify the product surface: mobile app, responsive web app, landing page section, dashboard, or prototype board.
2. Preserve the real workflow first: Token balance/recharge, Prompt debug, memory management, agent management, wearable ring controls, privacy/safety, or chat preview.
3. Apply the core visual system from `references/design-system.md` before inventing new colors, spacing, shadows, or components.
4. Use a mobile app screen as the primary artifact when the request says App or prototype. For a website, pair a left/side navigation or top workspace header with a constrained app-like content canvas.
5. Verify text fit, no overlapping controls, no card nesting clutter, and no single-color purple/blue dominance.

## Core Rules

- Make the UI feel like a polished emotional AI workspace, not a generic SaaS admin panel or marketing landing page.
- Use warm ivory and paper white as the dominant impression; reserve pastel pink, cyan, lavender, mint, and muted rose for accents.
- Use serif-style headings for screen titles and section hero titles; use clean Chinese system sans for body and controls.
- Use lucide icons for actions and navigation where available.
- Prefer compact real product controls over explanatory marketing copy: tabs, segmented pills, toggles, balance cards, memory cards, prompt textareas, chat bubbles, ring status panels.
- Keep cards at 18-24px radius, buttons/pills rounded, and shadows soft. Avoid harsh borders, black text, saturated gradients, dark cyber palettes, and decorative blobs.
- Use in-app text only for product content and labels. Do not add visible instructional copy that explains how the UI works.

## Layout Guidance

- Mobile app: create a realistic phone-like stack with status bar, app header, content cards, and bottom tabs. Keep screen content scrollable inside the app frame.
- Web app: use a 220-260px left rail, a top workspace header, and a main area that can showcase one app screen plus a supporting detail panel.
- Dashboard: lead with one large balance/status card, then 2x2 metrics, then management cards or lists.
- Prompt debug: place agent chips above a prompt textarea, actions below, and a chat preview directly after it.
- Memory management: show filters, memory type labels, confidence/status, source, edit/delete actions, and confirmation states.
- Wearable ring: show connection, battery, tactile/lighting modes, sleep/low mood/schedule triggers, and simple on/off toggles.

## Reference

Read `references/design-system.md` when implementing CSS variables, Tailwind tokens, component recipes, screen patterns, or a reusable visual style guide.

---

# Xinji Pencil App Design System

## Visual DNA

- Mood: intimate, polished, quiet, slightly editorial; an AI companion management workspace.
- Canvas: warm ivory and paper white first; pastel accents second.
- Density: app-like and operational, with enough breathing room for emotional product tone.
- Shape: 18-24px cards, 14-18px controls, full pills for chips/buttons/tabs.
- Texture: soft paper cards, hairline warm borders, mild translucent surfaces, low-contrast shadows.

## CSS Tokens

```css
:root {
  --xinji-canvas: #fbfaf6;
  --xinji-canvas-warm: #f7f4ef;
  --xinji-surface: rgba(255, 255, 252, 0.92);
  --xinji-surface-soft: rgba(255, 255, 252, 0.74);
  --xinji-border: rgba(226, 220, 211, 0.72);
  --xinji-border-strong: rgba(204, 193, 183, 0.54);

  --xinji-text: #2f2930;
  --xinji-text-soft: #77716b;
  --xinji-text-faint: #aaa39b;

  --xinji-pink: #f3e7ec;
  --xinji-rose: #d9a7bd;
  --xinji-lavender: #d7c9ea;
  --xinji-lilac-soft: #f3eff8;
  --xinji-cyan: #d8ecee;
  --xinji-mint: #bdd8d0;
  --xinji-gold-soft: #eee0c8;
  --xinji-action-fill: #e8dbe8;
  --xinji-chart-fill: #dca8c1;
  --xinji-chart-track: #efede8;

  --xinji-shadow: 0 18px 55px rgba(69, 58, 45, 0.08);
  --xinji-shadow-soft: 0 10px 32px rgba(90, 74, 63, 0.06);
  --xinji-radius-lg: 24px;
  --xinji-radius-md: 18px;
  --xinji-radius-sm: 12px;
}
```

## Typography

- Body/UI: `"PingFang SC", "Microsoft YaHei", ui-sans-serif, system-ui, sans-serif`.
- Display titles: `"Songti SC", "Noto Serif SC", Georgia, serif`.
- Eyebrow: 10-12px, uppercase, 0.18-0.22em letter spacing, muted warm gray.
- Numbers: Georgia or tabular sans; large Token numbers should feel editorial, not fintech-neon.
- Do not scale type by viewport width alone. Use `clamp()` only for major page titles.

## Backgrounds

Use warm ivory with subtle color washes:

```css
body {
  background:
    radial-gradient(circle at 12% 8%, rgba(234, 213, 222, 0.22), transparent 26%),
    radial-gradient(circle at 86% 14%, rgba(155, 221, 234, 0.18), transparent 28%),
    linear-gradient(135deg, var(--xinji-canvas), var(--xinji-canvas-warm));
}
```

Do not use large gradient orbs, bokeh blobs, neon glow, or dark purple cyberpunk backgrounds.

## Component Recipes

### Paper Card

```css
.xinji-card {
  border: 1px solid var(--xinji-border);
  border-radius: var(--xinji-radius-lg);
  background: var(--xinji-surface);
  box-shadow: var(--xinji-shadow-soft);
}
```

### Active Navigation Item

```css
.xinji-nav-active {
  border-radius: 16px;
  background: #fff;
  color: var(--xinji-text);
  box-shadow: 0 12px 30px rgba(80, 67, 53, 0.08);
}
```

### Icon Button

```css
.xinji-icon-button {
  display: grid;
  place-items: center;
  width: 40px;
  height: 40px;
  border: 1px solid var(--xinji-border);
  border-radius: 999px;
  color: #665f58;
  background: rgba(255, 255, 255, 0.76);
  box-shadow: var(--xinji-shadow-soft);
}
```

### CTA Pill

```css
.xinji-cta {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  min-height: 38px;
  padding: 0 14px;
  border: 0;
  border-radius: 999px;
  color: #5f5860;
  background: var(--xinji-action-fill);
  box-shadow: 0 10px 24px rgba(105, 92, 86, 0.09);
  font-weight: 800;
}
```

### Balance Card

Use for Token, connection, relationship state, daily usage, or memory health.

```css
.xinji-balance-card {
  display: flex;
  justify-content: space-between;
  gap: 16px;
  padding: 20px;
  border: 1px solid var(--xinji-border);
  border-radius: var(--xinji-radius-lg);
  background:
    linear-gradient(135deg, rgba(255, 255, 252, 0.95), rgba(243, 239, 248, 0.82)),
    radial-gradient(circle at 86% 15%, rgba(216, 236, 238, 0.62), transparent 36%);
  box-shadow: var(--xinji-shadow-soft);
}
```

### Metric Grid

- Use 2 columns on mobile and 4 columns only when space allows.
- Metric cards need an icon, a strong value, and one short label.
- Keep values large but not oversized: 24-32px in cards.

### Segmented Chips

- Use for agent selection, memory filters, modes, and privacy settings.
- Inactive: translucent white with warm border.
- Active: white surface with soft shadow.

### Prompt Editor

- Use a large rounded textarea in a paper card.
- Put agent chips above the editor.
- Place compact action pills below: "去复读优化", "保存", "测试".
- Pair with a chat preview using soft cyan AI bubbles and soft pink user bubbles.

### Memory Card

Required content: memory type, confidence or status, memory text, source, edit/delete actions.

Types to support:
- 长期偏好
- 当前事实
- 角色设定
- 临时情绪
- 敏感边界

### Agent Card

Use avatar tile, agent name, role, current status, and a chevron/action. Selected cards use a lavender border and white surface.

### Wearable Ring Panel

- Show a large soft ring/fingerprint visual or real device image when available.
- Include connection status and battery.
- Use setting rows for sleep greeting, low mood follow-up, AI proactive touch, and tap gesture.
- Toggles should be low-saturation mint with a white knob.

### Privacy/Safety Rows

Use rows for:
- 主动消息开关
- 静默时段
- 新增记忆确认
- 角色/现实隔离
- 高风险降级

## Screen Patterns

### Mobile App MVP

1. Status bar: time, connection, battery.
2. Header: small eyebrow, serif title, one icon button.
3. Primary card: Token balance, active agent, ring status, or privacy quiet mode.
4. Supporting cards/lists: metrics, memory cards, agent cards, settings rows.
5. Bottom tabs: 4-5 icon-only tabs with active pastel fill.

### Web Workspace

1. Left rail: brand, short product context, navigation list.
2. Main header: `UNION SOUL WORKSPACE` eyebrow and large serif title.
3. Main content: app canvas or dashboard grid.
4. Side panel: PRD mapping, current state, notes, or test output.

### Website Marketing Adaptation

Use the style without turning it into a generic hero:
- Make `心迹档案` or `Union Soul` a first-viewport signal.
- Use real app/device screenshots or an app frame as the hero asset.
- Keep text over or beside the product surface, not inside excessive nested cards.
- Hint at the next section below the fold.

## Icon Choices

Prefer lucide icons:
- Home, CircleDollarSign, Pencil, Database, Bot, Fingerprint, ShieldCheck
- Bell, Search, Settings2, Plus, Save, Trash2, SlidersHorizontal
- MessageCircle, HeartPulse, Moon, Clock3, Bluetooth, Zap

## Avoid

- Generic blue SaaS dashboards.
- Saturated purple gradients as the main brand impression.
- Dark neon, cyberpunk, black backgrounds, glass-only UIs.
- Large decorative blobs/orbs.
- Cards inside cards unless the inner card is a repeated list item.
- Oversized marketing copy inside an operational app surface.
- Visible instructions explaining UI mechanics.
