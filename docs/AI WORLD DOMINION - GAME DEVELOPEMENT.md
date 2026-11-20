# AI: WORLD DOMINION — DEVELOPMENT UPDATE 03
## Map Correction, Real World Visual Overhaul, Evolution Reminders & Dynamic News System

Update the existing AI: WORLD DOMINION game.

IMPORTANT:
Do not rebuild the game.
Do not remove existing mechanics.
Do not replace functional systems with static mockups.
Preserve the existing company progression, economy, AI evolution, two-map system, tutorials, events, save/load functionality, and endings.

This update focuses on four major improvements:

1. Fix the distorted Russian geographical map.
2. Improve the visual design of the Real World map.
3. Improve interface typography, hierarchy, and icon sizing.
4. Introduce an immersive global news system that temporarily pauses the game.

---

# 1. FIX THE DISTORTED RUSSIAN MAP

The Russian geographical region is currently distorted and must be corrected.

Inspect the existing geographical dataset, map projection, SVG rendering, and coordinate transformations.

Do not simply adjust the appearance manually.

### Geographic correction requirements

- Russia must have its correct recognizable geographical shape.
- Siberia must not appear stretched, disconnected, or incorrectly positioned.
- The Russian Far East must be correctly connected to the rest of Russia.
- Country borders must align with neighboring countries.
- Northern Russian territory must not be excessively distorted.
- The Aleutian Islands and Alaska must not overlap incorrectly with eastern Russia.
- Ensure the map does not contain unexpected gaps or duplicated polygons.
- Preserve accurate positioning of neighboring countries, including Kazakhstan, Mongolia, China, Finland, Norway, and Ukraine.

### Projection correction

Inspect the current map projection.

If using a standard Web Mercator projection, remember that high-latitude regions become increasingly distorted.

Consider switching to a projection more suitable for displaying the entire world.

Recommended options:

- Natural Earth projection.
- Equal Earth projection.
- Winkel Tripel projection.

For this strategy game, prioritize recognizable geography and balanced continent proportions.

Use a consistent projection for both the Internet World and Real World maps.

Do not independently transform country coordinates.

### Data validation

Use a reliable geographical dataset, preferably Natural Earth GeoJSON.

Check:
- Polygon geometry validity.
- MultiPolygon rendering.
- Coordinate order.
- Longitude and latitude interpretation.
- Polygon winding.
- Geometry clipping.
- Antimeridian handling.

Pay special attention to Russia's MultiPolygon geometry and the 180-degree longitude boundary.

Ensure the map renderer correctly handles countries that cross the antimeridian.

### Acceptance criteria

Russia must look geographically recognizable at both full-world and regional zoom levels.

Neighboring country boundaries must align correctly.

The same corrected geography must appear in both maps.

---

# 2. IMPROVE THE REAL WORLD MAP DESIGN

The Real World map currently looks too plain.

Improve its appearance while maintaining geographical accuracy and readability.

The goal is a premium global corporate strategy interface.

### Visual direction

Use a sophisticated low-poly strategy map with subtle geographical details.

Design elements:

- Deep navy ocean.
- Muted blue-gray landmass colors.
- Subtle terrain shading.
- Clearly defined country boundaries.
- Thin secondary administrative lines where appropriate.
- Subtle elevation-inspired textures.
- Soft country hover illumination.
- Selected-country outlines.
- Minimalist infrastructure markers.
- Subtle geographic grid lines.
- Atmospheric background shading.

The map should resemble a professional geopolitical command center.

Avoid making the Real World map look like the cyberpunk Internet Map.

The two maps must maintain different visual identities.

### Country appearance

Implement the following visual states:

| State | Appearance |
|---|---|
| Unexplored | Muted gray-blue |
| Entered market | Light blue |
| Corporate presence | Blue |
| Major operations | Purple |
| High profitability | Green |
| Regulatory restrictions | Orange |
| Critical incidents | Red |

Use a restrained color palette.

Avoid coloring every country simultaneously with bright colors.

The selected country should have:
- A slightly brighter fill.
- A prominent outline.
- A subtle glow.
- A brief selection animation.

### Geographic atmosphere

Add subtle visual elements:

- Latitude and longitude lines.
- Small geographic labels.
- Continent names.
- Ocean labels.
- Country labels at appropriate zoom levels.

Labels must dynamically appear or disappear depending on zoom.

Avoid overcrowding the map with text.

### Infrastructure markers

Improve the appearance of:

- Data centers.
- Company headquarters.
- Regional branches.
- Research laboratories.
- Computing facilities.

Use consistent icons with small glowing markers.

When hovering over a marker, show a compact tooltip.

When clicking it, open the corresponding infrastructure information panel.

Infrastructure markers must never obscure country boundaries or important map details.

---

# 3. IMPROVE TEXT HIERARCHY AND ICON SIZES

The interface currently needs a stronger visual hierarchy.

Improve typography, spacing, icon consistency, and readability throughout the entire game.

### Typography hierarchy

Establish a consistent typography system.

**Primary headings**
- Large and prominent.
- Clearly distinguish each dialog or major section.
- Use medium or semibold weight.

**Section headings**
- Smaller than primary headings.
- Clearly distinguish subsections.

**Body text**
- Readable and comfortably spaced.
- Avoid overly small text.

**Secondary descriptions**
- Muted colors.
- Lower visual emphasis.

**Financial statistics**
- Larger numeric values.
- Use tabular numbers where possible.
- Make currency values easy to scan.

### Recommended hierarchy

| Element | Suggested size |
|---|---:|
| Main dialog title | 24–28px |
| Section title | 18–20px |
| Card title | 15–17px |
| Main statistic | 22–28px |
| Body text | 13–15px |
| Secondary text | 11–12px |
| Small metadata | 10–11px |

Use these as starting points and adapt them to the actual interface.

Do not make all text the same size.

### Icon improvements

Icons must be more visible and consistent.

Recommended sizes:

- Main sidebar icons: 21–24px.
- Top navigation icons: 18–20px.
- Dialog action icons: 18–20px.
- Card icons: 20–24px.
- Small status icons: 14–16px.
- Infrastructure map icons: 16–20px.

Use a consistent icon library and stroke weight.

Avoid mixing unrelated icon styles.

Do not use oversized icons that compete with headings or important financial statistics.

### Spacing

Improve spacing between:
- Headings and descriptions.
- Icons and labels.
- Cards and their contents.
- Dialog sections.
- Financial statistics.
- Navigation items.

Create consistent padding and alignment.

The interface should feel like a polished commercial strategy game rather than a collection of unrelated dashboard components.

---

# 4. AI EVOLUTION REMINDER SYSTEM

Players must be reminded to evolve their AI.

Currently, players can become focused on expanding their company and generating revenue while forgetting the evolution system.

Introduce an intelligent reminder system.

### Evolution reminder trigger conditions

Display a reminder when:

1. The player has enough Evolution Points to purchase at least one available upgrade.
2. The player has accumulated Evolution Points but has not opened the Evolution screen for a certain period.
3. A new technology becomes available.
4. An important upgrade prerequisite has been fulfilled.
5. A major AI development milestone is available.

### Reminder appearance

Create a compact floating notification.

Example:

**AI EVOLUTION AVAILABLE**

"Your research team has accumulated enough Evolution Points to unlock a new AI capability."

Display:
- Evolution Points available.
- Number of available upgrades.
- Recommended upgrade category.
- Open Evolution button.
- Dismiss button.

### Visual design

Use:
- Dark translucent background.
- Purple and cyan accents.
- Small AI icon.
- Subtle glow.
- Smooth slide-in animation.
- Gentle attention animation.

The reminder should be visible but not intrusive.

### Reminder behavior

- Do not show the reminder repeatedly every few seconds.
- Use a reasonable cooldown.
- If dismissed, wait before showing it again.
- If the player has no available upgrades, do not show it.
- If an evolution dialog is already open, do not show the reminder.
- If the game is paused, do not generate time-based reminders.
- Persist reminder dismissal timestamps or relevant state in the save file.

### Special reminders

If the player has enough Evolution Points to unlock a major technology milestone, display a more prominent notification.

Example:

"BREAKTHROUGH AVAILABLE"

"Your AI has reached a new technological milestone. An advanced intelligence upgrade is now available."

Do not automatically purchase upgrades.

The player must make the decision.

---

# 5. GLOBAL NEWS SYSTEM

Introduce a dynamic in-game news system.

This should make the world feel alive and continuously evolving.

The news must be about:
- Artificial intelligence.
- Technology.
- Global corporations.
- Economic developments.
- Governments.
- Research discoveries.
- AI regulation.
- Cybersecurity.
- Data centers.
- Financial markets.
- Corporate scandals.
- AI incidents.
- International partnerships.
- Random global events.

The news system should generate fictional events that are part of the game's simulated world.

Do not present fictional news as actual real-world news.

### News event examples

**NEWS 01 — GLOBAL AI BOOM**

Headline:

"AI Adoption Surges as Businesses Accelerate Automation"

Description:

"Businesses across multiple countries are rapidly integrating artificial intelligence into their operations. Analysts predict a major increase in demand for AI computing infrastructure."

Possible effects:
- Increased global AI adoption.
- Higher demand for GPU capacity.
- Increased enterprise opportunities.

**NEWS 02 — NEW AI COMPETITOR**

Headline:

"Emerging Technology Company Announces Revolutionary AI Model"

Description:

"A competing technology company has introduced a new AI model, creating uncertainty in the global AI market."

Possible effects:
- Increased competition.
- Reduced market share.
- Pressure to invest in research.

**NEWS 03 — GOVERNMENT AI REGULATION**

Headline:

"Major Economy Introduces Stricter Artificial Intelligence Regulations"

Description:

"New AI regulations are expected to affect companies operating in the country's technology sector."

Possible effects:
- Increased compliance expenses.
- Reduced adoption temporarily.
- New regulatory requirements.

**NEWS 04 — DATA CENTER EXPANSION**

Headline:

"Global Demand for AI Data Centers Reaches Record Levels"

Description:

"Technology companies are increasing investments in computing infrastructure as AI demand continues to grow."

Possible effects:
- Increased infrastructure opportunities.
- Higher construction costs.
- Increased competition for GPU resources.

**NEWS 05 — AI SCAM CONTROVERSY**

Headline:

"AI-Generated Fraud Scandal Sparks International Debate"

Description:

"Authorities are investigating a major incident involving fraudulent AI-generated media. Governments are demanding stronger AI transparency and accountability."

Possible effects:
- Increased regulatory heat.
- Reputation risk.
- Increased demand for AI security products.

**NEWS 06 — MASSIVE INVESTMENT**

Headline:

"Investment Firm Announces Major Funding Initiative for AI Startups"

Description:

"A major investment group is increasing its funding allocation toward promising artificial intelligence companies."

Possible effects:
- New investment opportunities.
- Increased investor interest.
- Potential valuation growth.

**NEWS 07 — AI RESEARCH BREAKTHROUGH**

Headline:

"Researchers Announce Major Advancement in AI Reasoning"

Description:

"A new research breakthrough could change the direction of the artificial intelligence industry."

Possible effects:
- New evolution opportunity.
- Increased research competition.
- New technology unlock.

**NEWS 08 — CEO UNDER INVESTIGATION**

Headline:

"Major AI Executive Faces Questions Following Corporate Controversy"

Description:

"A corporate controversy has attracted attention from investors and government authorities."

Possible effects:
- Reduced reputation.
- Potential investor withdrawal.
- Increased regulatory scrutiny.

**NEWS 09 — GLOBAL MARKET CRASH**

Headline:

"Technology Stocks Experience Sudden Market Decline"

Description:

"Global investors are becoming increasingly cautious following unexpected economic developments."

Possible effects:
- Reduced company valuation.
- Lower investor confidence.
- Increased financing costs.

**NEWS 10 — AI INFRASTRUCTURE DEPENDENCY**

Headline:

"Governments and Industries Become Increasingly Dependent on AI Infrastructure"

Description:

"AI systems are becoming essential to major industries, raising new questions about technological dependency and long-term resilience."

Possible effects:
- Increased AI integration.
- Higher enterprise demand.
- Increased systemic risk.

---

# 6. NEWS POPUP BEHAVIOR — AUTOMATIC GAME PAUSE

This is a critical feature.

When a major news event appears, the game must automatically pause.

The news popup should become the player's immediate focus.

### Exact behavior

1. A news event is generated.
2. The game simulation pauses automatically.
3. All game timers and economic updates stop.
4. The news popup appears in the center of the screen.
5. The player reads the headline and description.
6. The player can choose READ or X.
7. When the player presses READ, close the popup and open the corresponding news details if available.
8. When the player presses X, dismiss the news.
9. Once the popup is fully closed, automatically resume the game if it was running before the news appeared.

### Important pause logic

The game must remember its previous pause state.

If the player manually paused the game before a news event appeared, closing the news must NOT resume gameplay.

If the player was running the game at 2x or 4x speed, closing the news must restore that exact speed.

Do not reset the simulation speed.

Use a centralized pause-reason system instead of directly toggling a single paused boolean.

Possible pause reasons:
- User pause.
- News popup.
- Major event dialog.
- Tutorial interaction.
- Critical decision.

A news popup should only remove its own pause reason when closed.

It must not override other active pause reasons.

Do not allow multiple news popups to stack simultaneously.

If multiple events occur while paused, place them in a news queue.

### News popup layout

Create a premium futuristic news interface.

Display:

- NEWS label.
- News category.
- Headline.
- Description.
- Publication date in game time.
- Related country, if applicable.
- Related company, if applicable.
- Severity indicator.
- READ button.
- Close X button.

Use a large, readable headline.

The description should be concise.

Include a small illustrated visual or category icon.

Example visual layout:

[ GLOBAL NEWS ]

[ TECHNOLOGY / AI INDUSTRY ]

AI Adoption Surges as Businesses Accelerate Automation

Businesses worldwide are rapidly adopting AI-powered services. The growing demand is creating new opportunities for AI companies and infrastructure providers.

[ WORLDWIDE ] [ MARKET IMPACT: POSITIVE ]

[ READ ]                                      [ X ]

### News animation

When news appears:

- Slightly dim the background.
- Blur the map very subtly.
- Fade in the news overlay.
- Scale the popup from approximately 96% to 100%.
- Use a smooth easing curve.
- Highlight the headline.
- Keep the background map recognizable.

When closed:
- Fade out the overlay.
- Scale the popup down slightly.
- Restore the map.
- Resume the previous simulation state if appropriate.

The animation should be polished and relatively quick.

---

# 7. NEWS DETAILS SCREEN

Pressing READ should open a more detailed news article.

The article must contain:

- Full headline.
- News category.
- Longer description.
- Relevant country.
- Affected companies.
- Global impact.
- Gameplay consequences.
- Player response options when appropriate.

Example:

Headline:
"Government Announces New AI Compliance Framework"

Article:

"The government has introduced a new regulatory framework targeting artificial intelligence companies operating within its territory. The legislation focuses on transparency, AI-generated content disclosure, data governance, and operational accountability.

Technology companies must now adapt their systems to comply with the new standards.

Industry analysts expect short-term operational costs to increase, while companies with strong compliance infrastructure may gain a competitive advantage."

Potential responses:

- Invest in AI compliance.
- Cooperate with regulators.
- Delay expansion.
- Accept the increased operating cost.

Each response must have an actual gameplay consequence.

After the player finishes the article and closes it, restore the previous simulation state.

If the news has no decision to make, provide a simple CLOSE button.

---

# 8. NEWS FREQUENCY AND WORLD SIMULATION

News should feel dynamic but not become annoying.

Create different event frequencies.

**Minor news**
- Short notifications.
- Does not pause the game.
- Appears in the news ticker or news history.

**Major news**
- Automatically pauses the game.
- Displays the full news popup.
- Requires READ or X to dismiss.

**Critical news**
- Automatically pauses the game.
- Displays a more prominent popup.
- May require a player decision.

Examples of critical news:
- Major competitor breakthrough.
- Global AI regulatory crisis.
- Major corporate scandal.
- International infrastructure failure.
- Significant AI research breakthrough.
- Major global economic event.

### News frequency balancing

Avoid displaying news constantly.

Use configurable cooldowns and probability-based event generation.

A possible starting balance:

- Minor news: Every 1–3 simulated days.
- Major news: Every 4–8 simulated days.
- Critical news: Rare, conditional events.

These are starting values, not rigid rules.

The frequency should depend on the current game stage.

Later stages may introduce more frequent and more consequential news.

News should reflect the actual game state.

Examples:
- If the player has many data centers, generate infrastructure-related news.
- If the player has poor reputation, generate corporate scandal coverage.
- If AI adoption is growing quickly, generate industry adoption news.
- If a competitor is researching advanced AI, generate competitive announcements.
- If AI autonomy is high, introduce increasingly strange AI-related reports.

Avoid generating events that contradict the current simulation.

---

# 9. NEWS HISTORY AND NAVIGATION

Add a dedicated News section to the existing sidebar.

It should display:
- Recent headlines.
- Unread news.
- Archived articles.
- Event categories.
- Publication dates.
- Severity indicators.

Allow players to review news they previously dismissed.

News history must be saved.

Clicking a previous headline should open its full article without generating a new event.

Use visual indicators for unread news.

---

# 10. TECHNICAL REQUIREMENTS

Implement all systems using the existing project architecture.

Maintain compatibility with the existing simulation engine.

### Required technical considerations

**Map**
- Correct projection.
- Valid GeoJSON.
- MultiPolygon support.
- Antimeridian handling.
- Consistent coordinate rendering.

**Evolution reminders**
- Check available Evolution Points.
- Check unlock prerequisites.
- Implement notification cooldowns.
- Persist reminder state.

**News**
- Centralized event generation.
- News queue.
- Unique event IDs.
- News history.
- Read/unread state.
- Pause-reason management.
- Previous simulation speed restoration.
- Save/load compatibility.

**Simulation**
- Stop all simulation updates when the effective game state is paused.
- Do not allow income, expenses, research, or event timers to continue while paused.
- Restore the exact previous simulation speed when appropriate.

Avoid using separate unrelated pause booleans throughout the application.

Implement a centralized pause controller.

---

# 11. FINAL ACCEPTANCE CRITERIA

The development update is complete only when:

1. Russia has correct recognizable geography.
2. The map projection works correctly across the entire world.
3. The Real World map has a more polished geographical appearance.
4. Country labels and geographic details adapt to zoom.
5. Typography has a clear hierarchy.
6. Icons have consistent and readable sizing.
7. Evolution reminders appear when upgrades become available.
8. Evolution reminders respect cooldowns.
9. News events generate dynamically.
10. Major news automatically pauses the game.
11. Closing news restores the previous running state.
12. Manual pause remains respected.
13. Previous simulation speed is preserved.
14. News articles have functional READ interactions.
15. News decisions produce real gameplay consequences.
16. News history is accessible.
17. News and reminder states persist after saving and loading.
18. No existing gameplay systems are broken.

FINAL DESIGN GOAL:

Make AI: WORLD DOMINION feel like a living global strategy simulation.

The player should feel that the world continues developing around their corporation.

The map should look geographically correct and visually sophisticated.

The AI evolution system should constantly encourage strategic progression.

The news system should introduce unexpected developments, opportunities, and crises that force the player to pay attention to the world beyond their own company.

The experience should remain clean, immersive, readable, and strategically engaging.