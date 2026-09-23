reference repo:https://github.com/addyosmani/agent-skills

Skill name - > using-agent-skills
What it does -> Maps incoming work to the right skill workflow and defines shared operating rules
Use when -> Starting a session or deciding which skill applies
Skill name - > interview-me
What it does -> One-question-at-a-time interview that extracts what the user actually wants instead of what they think they should want, until ~95% confidence
Use when -> The ask is underspecified, or the user invokes "interview me" / "grill me"
Skill name - > idea-refine
What it does -> Structured divergent/convergent thinking to turn vague ideas into concrete proposals
Use when -> You have a rough concept that needs exploration
Skill name - > spec-driven-development
What it does -> Write a PRD covering objectives, commands, structure, code style, testing, and boundaries before any code
Use when -> Starting a new project, feature, or significant change
Skill name - > constraint-driven-development
What it does -> Interviews you for a quality bar with sane default thresholds, writes CONSTRAINTS.md, places each check by cost, and catches agents silencing checks or skipping tests to get green
Use when -> No standards are written down, or an agent is producing more than anyone reads
Skill name - > planning-and-task-breakdown
What it does -> Decompose specs into small, verifiable tasks with acceptance criteria and dependency ordering
Use when -> You have a spec and need implementable units
Skill name - > incremental-implementation
What it does -> Thin vertical slices - implement, test, verify, commit. Feature flags, safe defaults, rollback-friendly changes
Use when -> Any change touching more than one file
Skill name - > test-driven-development
What it does -> Red-Green-Refactor, test pyramid (80/15/5), test sizes, DAMP over DRY, Beyonce Rule, browser testing
Use when -> Implementing logic, fixing bugs, or changing behavior
Skill name - > context-engineering
What it does -> Feed agents the right information at the right time - rules files, context packing, MCP integrations
Use when -> Starting a session, switching tasks, or when output quality drops
Skill name - > source-driven-development
What it does -> Ground every framework decision in official documentation - verify, cite sources, flag what's unverified
Use when -> You want authoritative, source-cited code for any framework or library
Skill name - > doubt-driven-development
What it does -> Adversarial fresh-context review of every non-trivial decision in-flight - CLAIM → EXTRACT → DOUBT → RECONCILE → STOP, with optional user-authorized cross-model escalation
Use when -> Stakes are high (production, security, irreversible), working in unfamiliar code, or a confident output is cheaper to verify now than to debug later
Skill name - > frontend-ui-engineering
What it does -> Component architecture, design systems, state management, responsive design, WCAG 2.1 AA accessibility
Use when -> Building or modifying user-facing interfaces
Skill name - > api-and-interface-design
What it does -> Contract-first design, Hyrum's Law, One-Version Rule, error semantics, boundary validation
Use when -> Designing APIs, module boundaries, or public interfaces
Skill name - > browser-testing-with-devtools
What it does -> Chrome DevTools MCP for live runtime data - DOM inspection, console logs, network traces, performance profiling
Use when -> Building or debugging anything that runs in a browser
Skill name - > debugging-and-error-recovery
What it does -> Five-step triage: reproduce, localize, reduce, fix, guard. Stop-the-line rule, safe fallbacks
Use when -> Tests fail, builds break, or behavior is unexpected
Skill name - > code-review-and-quality
What it does -> Five-axis review, change sizing (~100 lines), severity labels (Nit/Optional/FYI), review speed norms, splitting strategies
Use when -> Before merging any change
Skill name - > code-simplification
What it does -> Chesterton's Fence, Rule of 500, reduce complexity while preserving exact behavior
Use when -> Code works but is harder to read or maintain than it should be
Skill name - > security-and-hardening
What it does -> OWASP Top 10 prevention, auth patterns, secrets management, dependency auditing, three-tier boundary system
Use when -> Handling user input, auth, data storage, or external integrations
Skill name - > performance-optimization
What it does -> Measure-first approach - Core Web Vitals targets, profiling workflows, bundle analysis, anti-pattern detection
Use when -> Performance requirements exist or you suspect regressions
Skill name - > git-workflow-and-versioning
What it does -> Trunk-based development, atomic commits, change sizing (~100 lines), the commit-as-save-point pattern
Use when -> Making any code change (always)
Skill name - > ci-cd-and-automation
What it does -> Shift Left, Faster is Safer, feature flags, quality gate pipelines, failure feedback loops
Use when -> Setting up or modifying build and deploy pipelines
Skill name - > deprecation-and-migration
What it does -> Code-as-liability mindset, compulsory vs advisory deprecation, migration patterns, zombie code removal
Use when -> Removing old systems, migrating users, or sunsetting features
Skill name - > documentation-and-adrs
What it does -> Architecture Decision Records, API docs, inline documentation standards - document the why
Use when -> Making architectural decisions, changing APIs, or shipping features
Skill name - > observability-and-instrumentation
What it does -> Structured logging, RED metrics, OpenTelemetry tracing, symptom-based alerting - instrument as you build
Use when -> Adding telemetry, or shipping anything that runs in production
Skill name - > shipping-and-launch
What it does -> Pre-launch checklists, feature flag lifecycle, staged rollouts, rollback procedures, monitoring setup
Use when -> Preparing to deploy to production