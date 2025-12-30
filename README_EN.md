# Claude Agent Orchestration System

AI Agent-based Software Development Lifecycle Management System

## Overview

21 specialized agents automatically orchestrate a 6-phase development process, providing a complete development workflow from planning to deployment.

## Architecture

```
┌─────────────────────────────────────────────────────────────────────────┐
│                         🎯 ORCHESTRATOR                                  │
│                   (Workflow Orchestration)                               │
└─────────────────────────────────────────────────────────────────────────┘
                                    │
    ┌───────────────────────────────┼───────────────────────────────┐
    ▼                               ▼                               ▼
┌─────────────┐             ┌─────────────┐             ┌─────────────┐
│  📋 PHASE 1 │             │  🎨 PHASE 2 │             │  🔍 PHASE 3 │
│  Planning   │             │   Design    │             │   Review    │
└──────┬──────┘             └──────┬──────┘             └──────┬──────┘
       │                           │                           │
       ▼                           ▼                           ▼
┌─────────────┐             ┌─────────────┐             ┌─────────────┐
│  💻 PHASE 4 │             │  ✅ PHASE 5 │             │  🚀 PHASE 6 │
│ Development │             │   Testing   │             │ Deployment  │
└─────────────┘             └─────────────┘             └─────────────┘
```

## Agent List

### Phase 1: Planning
| Agent | Role |
|-------|------|
| `planner` | Requirements analysis, planning documentation |
| `researcher` | Technology stack research, reference analysis |

### Phase 2: UX/UI Design
| Agent | Role |
|-------|------|
| `ux-designer` | User flows, wireframes |
| `ui-designer` | Visual design, component specs |
| `prototyper` | Interactive prototypes |
| `design-system-manager` | Design system consistency |

### Phase 3: Review
| Agent | Role |
|-------|------|
| `tech-reviewer` | Technical feasibility review |
| `ux-reviewer` | UX heuristic evaluation |

### Phase 4: Development
| Agent | Role |
|-------|------|
| `architect` | System design, API, DB schema |
| `developer` | Backend implementation |
| `ui-developer` | Frontend implementation |
| `code-reviewer` | Code review, quality inspection |

### Phase 5: Testing
| Agent | Role |
|-------|------|
| `tester` | Unit/Integration/E2E testing |
| `security-auditor` | Security vulnerability scanning |
| `accessibility-auditor` | WCAG accessibility audit |
| `ui-qa` | Visual/cross-browser testing |
| `performance-tester` | Performance/load testing |
| `qa-engineer` | Final QA, release approval |

### Phase 6: Deployment
| Agent | Role |
|-------|------|
| `devops-engineer` | Infrastructure, CI/CD, monitoring |
| `deployer` | Deployment execution, rollback management |

### Exception Handling
| Agent | Role |
|-------|------|
| `debugger` | Debugging, error analysis and fixes |

## Usage

### Run Full Workflow
```
"Develop user authentication feature with full process"
```

### Run Specific Phase
```
"Just do UX design for this feature"
"Review the code"
"Run performance tests"
```

### Trigger Examples
| Trigger | Agent Called |
|---------|-------------|
| "plan this" | planner |
| "research tech" | researcher |
| "UX design" | ux-designer |
| "UI design" | ui-designer |
| "prototype" | prototyper |
| "tech review" | tech-reviewer |
| "backend dev" | developer |
| "frontend dev" | ui-developer |
| "code review" | code-reviewer |
| "test" | tester |
| "security scan" | security-auditor |
| "accessibility check" | accessibility-auditor |
| "performance test" | performance-tester |
| "final QA" | qa-engineer |
| "deploy" | deployer |

## Directory Structure

```
claude-orche/
├── agents/                    # Agent definitions
│   ├── CLAUDE.md             # Project overview
│   ├── orchestrator.md       # Main orchestrator
│   ├── planner.md
│   ├── researcher.md
│   ├── ux-designer.md
│   ├── ui-designer.md
│   ├── prototyper.md
│   ├── design-system-manager.md
│   ├── tech-reviewer.md
│   ├── ux-reviewer.md
│   ├── architect.md
│   ├── developer.md
│   ├── ui-developer.md
│   ├── code-reviewer.md
│   ├── tester.md
│   ├── security-auditor.md
│   ├── accessibility-auditor.md
│   ├── ui-qa.md
│   ├── performance-tester.md
│   ├── qa-engineer.md
│   ├── devops-engineer.md
│   ├── deployer.md
│   └── debugger.md
├── PLAN.md                   # Improvement plan and progress
├── README.md                 # Korean documentation
└── README_EN.md              # This file
```

## Key Features

### Gate Checks
Automatic verification at each phase completion:
- Phase 1: Planning document exists, requirements section verified
- Phase 2: UX/UI design directories, prototype verified
- Phase 3: Review approval confirmed
- Phase 4: lint, type-check, build passed
- Phase 5: Test coverage, security/accessibility checks
- Phase 6: Health check, deployment status, monitoring

### Retry Policy
- Maximum retries: 3 attempts
- 1st: Same agent retries after fix
- 2nd: Retry with additional context
- 3rd: Debugger agent intervention
- Beyond 3: Escalation to user

### Parallel Processing
- `planner` + `researcher` (Planning)
- `tech-reviewer` + `ux-reviewer` (Review)
- `developer` + `ui-developer` (Development)
- `tester` + `security-auditor` + `accessibility-auditor` + `ui-qa` + `performance-tester` (Testing)
- `devops-engineer` + `deployer` (Deployment)

## Tech Stack

Supported technologies by agents:
- **Frontend**: React 18, Next.js 14, TypeScript 5.3
- **State**: Zustand 4.4
- **Styling**: Tailwind CSS 3.4
- **Testing**: Jest, React Testing Library, Playwright
- **Backend**: Node.js, Prisma ORM
- **CI/CD**: GitHub Actions, Docker, Kubernetes
- **Monitoring**: Prometheus, Grafana

## License

MIT License
