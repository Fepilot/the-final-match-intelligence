I want you to take full ownership of this project from raw data to finished interactive application.

Build an interactive data experience called:

# THE FINAL · MATCH INTELLIGENCE

**Spain vs Argentina · World Cup Final 2026**

This is a FerPilot exploration of how AI can transform raw sports data into an interactive story.

I have attached the available source files for the match, including event data, documentation and a post\-match report.

Your job is to:

**UNDERSTAND → VALIDATE → ANALYZE → TRANSFORM → DESIGN → BUILD → TEST**

Do not ask me to manually clean or transform the data unless it is absolutely impossible for you to continue.

---

# 1\. UNDERSTAND THE DATA

Start by inspecting every attached file.

Determine:

- what each file contains;
- how the files relate to each other;
- available event types;
- player and team identifiers;
- timestamps;
- periods;
- coordinates;
- passes;
- shots;
- defensive events;
- substitutions;
- formations;
- outcomes;
- available statistics.

Read the data dictionary carefully.

Distinguish strictly between:

**EVENT DATA**

and

**TRACKING DATA**

Coordinates X/Y attached to events are EVENT DATA.

They must never be represented as continuous positions of players.

Do not fabricate tracking.

Do not fabricate ball positions.

Do not fabricate player movements between events.

---

# 2\. VALIDATE THE DATA

Before analyzing the match, audit data quality.

Check:

- duplicated IDs;
- chronological ordering;
- missing values;
- inconsistent player/team IDs;
- coordinate consistency;
- event ordering;
- period information;
- metadata inconsistencies.

There is a known potential inconsistency between the score stored in the event dataset metadata and the score shown in the post\-match report.

Investigate this discrepancy using the actual evidence available in the files.

Inspect all Goal\-related events and determine whether the score metadata appears stale or inconsistent.

Do not silently modify source data.

Document any correction or interpretation you need to make.

Maintain a clear internal distinction between:

**SOURCE** Directly present in the source data.

**DERIVED** Calculated reproducibly from source data.

**UNAVAILABLE** Cannot be reliably determined.

Never replace UNAVAILABLE data with estimates.

---

# 3\. ANALYZE THE MATCH

Now analyze the complete event dataset.

The main question driving the experience is:

# How was this World Cup Final really decided?

Explore the match chronologically and spatially.

Where supported by the data, investigate:

- territorial progression;
- passing patterns;
- progressive passes;
- entries into the final third;
- entries into the penalty area;
- recoveries;
- interceptions;
- turnovers;
- defensive actions;
- shots;
- shot locations;
- event density;
- player involvement;
- possession sequences when they can be reconstructed reliably;
- differences between Spain and Argentina;
- differences between first half, second half and extra time;
- changes in attacking behaviour;
- spatial patterns preceding important moments.

Do not stop at obvious statistics.

Look for patterns that make someone think:

**"I hadn't noticed that."**

Identify the strongest evidence\-based insights.

Every insight must be traceable to the underlying events.

Do not infer off\-ball behaviour, player velocity, continuous tactical shape, pressure based on proximity or pitch control because tracking data is not available.

---

# 4\. FIND THE STORY

I don't want a dashboard full of metrics.

I want an interactive story.

Identify the most interesting moments and turning points supported by the data.

Create approximately 5\-8 strong STORY MOMENTS.

Give each one a short editorial title.

Examples of the tone:

"THE FIRST WARNING"

"SPAIN FINDS THE SPACE"

"ARGENTINA LOSES THE EXIT"

"THE MATCH TILTS"

"THE DECISIVE SEQUENCE"

These are style examples only.

Do not use them unless supported by the actual data.

Each story moment should map to:

- a match time;
- relevant events;
- players;
- pitch locations;
- an insight;
- visual evidence.

Users must be able to click a story moment and SEE THE EVIDENCE on the pitch.

---

# 5\. PREPARE THE DATA YOURSELF

Prepare whatever internal transformations are necessary for the application.

You may clean, order and transform the source data as needed.

Where useful, derive reproducible metrics from the source events.

Document derived metrics.

Do not ask me to manually create intermediate CSV or Excel files if you can perform the transformation yourself.

Keep the original source data unchanged.

---

# 6\. BUILD THE EXPERIENCE

Build the finished interactive application.

The experience is called:

# THE FINAL

Subtitle:

**MATCH INTELLIGENCE**

Spain vs Argentina

World Cup Final · 2026

Subtle branding:

**FerPilot · Football Intelligence Exploration**

The application should make someone feel like they can **relive the match through its data**.

---

# 7\. THE INTERACTIVE PITCH

The football pitch must be the hero of the experience.

Do NOT make KPI cards or conventional charts the visual center.

Create a premium interactive football pitch.

Spain:

strong, elegant red.

Argentina:

light blue.

Dark premium background.

Dark green football pitch.

Use only real event coordinates.

Visualize, when available:

passes as directional trajectories;

shots as distinctive actions;

recoveries;

interceptions;

defensive actions;

fouls;

turnovers;

other significant event types.

Animate transitions between EVENTS but never imply that the animation represents actual player tracking.

---

# 8\. MATCH TIMELINE

Create a major interactive timeline spanning the entire match including extra time where present.

Include:

**Play**

**Pause**

Timeline scrubber

Playback speed

Period selector

Team selector

Player selector

Event type selector

Story Moment bookmarks

Important events should be visually marked on the timeline.

Moving through time should update the pitch.

The result should feel like exploring the match rather than filtering a database.

---

# 9\. PLAYER EXPLORER

Allow me to select a player.

When selected, isolate their available actions.

Depending on what exists in the data, show:

- passes;
- shots;
- recoveries;
- defensive actions;
- event locations;
- involvement;
- progressive actions;
- spatial distribution.

Do not create a continuous movement heatmap.

Event\-density visualizations are acceptable, but label them accurately.

---

# 10\. STORY MODE

Create a prominent mode called:

# WHAT THE DATA TELLS US

This should be one of the signature features.

Each insight should be interactive.

When I select an insight, automatically update:

- pitch;
- timeline;
- period;
- relevant events;
- relevant players;
- supporting metrics.

The application should not simply SAY what happened.

It should SHOW WHY the data supports the conclusion.

Think:

**Insight → Evidence → Exploration**

---

# 11\. COMPARISON MODE

Create an elegant way to compare:

Spain vs Argentina

and individual players where appropriate.

Prioritize visual comparisons rather than tables.

Possible comparisons can include metrics such as:

- passing;
- progression;
- attempts;
- recoveries;
- defensive actions;
- spatial distribution;

but ONLY where supported by available data.

Never include a metric solely because it would look interesting.

---

# 12\. VISUAL DESIGN

This must NOT look like:

Power BI;

a spreadsheet;

a traditional corporate dashboard;

a generic football statistics website.

The design concept is:

# SPORTS TELEMETRY × EDITORIAL STORYTELLING × EXECUTIVE ANALYTICS

Make it:

cinematic;

minimal;

premium;

dark;

data\-driven;

interactive;

editorial;

modern.

Use typography aggressively.

Use animations subtly.

Use whitespace.

Reduce unnecessary borders.

Avoid a grid of 20 KPI cards.

Avoid visual clutter.

---

# 13\. FERPILOT DESIGN PRINCIPLE

Apply this philosophy throughout the application:

# DON'T SHOW ME MORE DATA.

# HELP ME SEE WHAT MATTERS.

Every visualization should answer a question.

Every metric should support a story.

Every interaction should help discovery.

If something merely displays data without improving understanding, simplify it or remove it.

---

# 14\. ABOUT THE DATA

Create an elegant, discreet section:

**ABOUT THE DATA**

Explain transparently:

- data sources;
- event\-data limitations;
- derived metrics;
- unavailable metrics;
- known inconsistencies.

Explicitly explain that this experience uses event data rather than continuous player tracking.

If confirmed from the source files, emphasize that the visualization represents the recorded match events rather than simulated tracking.

Data credibility is part of the product.

---

# 15\. QUALITY CONTROL

Before considering the application finished, critically audit your own work.

Review it from three perspectives:

## FOOTBALL ANALYST

Are the conclusions supported by the match data?

## DATA SCIENTIST

Are calculations, coordinates and derived metrics defensible?

## EXECUTIVE USER

Can someone understand the story without knowing the underlying dataset?

Then test:

- timeline;
- pitch mapping;
- period switching;
- player filters;
- team filters;
- event filters;
- Story Moments;
- insights;
- score representation;
- responsive behaviour;
- interactions;
- application errors.

Fix problems you identify.

---

# 16\. FINAL DESIGN PASS

Finally, perform one ruthless simplification pass.

Do not add charts simply to make the application appear sophisticated.

For every component ask:

**"Does this help me understand the final?"**

If not:

remove it;

simplify it;

or integrate it into the story.

The finished application should feel like an immersive interactive story built from real football data.

Not a dashboard.

Not an AI prototype.

A finished data product.

The output I expect from this task is the working interactive application itself.

Take ownership of the complete process from the attached raw data to the finished experience.

