Discovery → Design → Build → Verify → Ship → Learn
    ↑                                         │
    └──────────── Approved next cycle ─────────┘
```

The orchestrator maintains shared context, delegates work, checks deliverables, tracks risks, and communicates with the founder. Every stage gate requires explicit human approval.

Three workflow models are defined:

- **Strict stage gates:** complete each stage before starting the next.
- **Iterative slices:** deliver small end-to-end increments, with gates for each slice.
- **Hybrid:** complete discovery and design first, then build, verify, and ship in slices.

The prompts emphasize evidence-based discovery, measurable outcomes, test-driven development, Gherkin acceptance criteria, security reviews, and post-launch learning. These are instructions for the agents; enforcement depends on the configured tools and runtime.

## Getting started

1. Clone the repository:

   ```bash
   git clone https://github.com/mr-dap-lab/startupswarm.git
   cd startupswarm
   ```

2. Start with [`01-context-owner-orchestrator.md`](01-context-owner-orchestrator.md) as the coordinating agent's instructions.
3. Use the numbered files `02` through `23` as the specialist agents' instructions in your GrokBot environment.
4. Adapt model and tool settings to your runtime, and supply the supporting resources listed below.
5. Give the orchestrator a product brief with your target users, problem, constraints, and measurable goals. Choose a workflow model at kickoff.

### Example kickoff prompt

```text
Start a StartupSwarm mission for a customer-feedback tool for small SaaS teams.

Problem: Feedback is scattered across support tickets, email, and chat.
Target users: Founders and product managers at small SaaS companies.
Goal: Help users turn incoming feedback into a prioritized product backlog.
Constraints: Propose a small MVP and present cost estimates for approval.
Workflow: Hybrid.

Identify missing information, establish measurable success criteria,
and begin discovery. Present the gate package for my approval before
advancing to the next stage.
```

## Expected mission outputs

The role definitions specify a workspace organized around each product mission:

```text
missions/<product-slug>/
├── mission-state.md     # Decisions, assignments, risks, and approvals
├── success-criteria.md  # Customer outcomes and measurable targets
├── discovery/          # Research, evidence, PRD, and success metrics
├── specs/              # User flows, journeys, and scenarios
├── design/             # Brand, key screens, and craft reviews
├── architecture/       # System design, ADRs, data models, threat model
├── backlog/            # Epics, stories, and Gherkin acceptance criteria
├── gtm/                # Positioning, sales, content, and funnel plans
├── ship/               # Release plans and dependency tracking
└── src/                # Product implementation
```

These artifacts are intended to be created during a mission; they are not bundled project results.

## Runtime and supporting resources

The repository currently provides 23 role-definition files and a README. It does not include a runnable application, an automated GrokBot installer, or a configured orchestration runtime.

Several prompts reference resources that are not included:

- `standards/nfr-baseline.md`
- `standards/customer-love.md`
- A `design-system` skill
- `.claude/hooks/fast-checks.sh`

Specialist files also contain Claude-style model and tool metadata. Configure equivalent capabilities in your chosen environment and provide or adapt the referenced resources before relying on the full workflow.

## Contributing

Improvements to role instructions, handoff contracts, runtime setup documentation, and example missions are welcome. Keep responsibilities clear and distinguish verified results from assumptions.
