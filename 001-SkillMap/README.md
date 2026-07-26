# SkillMap

> An explainable career intelligence platform for students, graduates, working professionals, employers, and higher education institutions.

## Overview

SkillMap is a multi-workspace career intelligence platform designed to help users understand their career options, identify skill gaps, and plan their next steps.

Instead of providing generic job suggestions, SkillMap evaluates information such as a user’s education, skills, interests, experience level, and work preferences. It then produces explainable career recommendations, compatibility scores, development priorities, and structured career roadmaps.

The platform also connects the wider career ecosystem through dedicated workspaces for candidates, employers, and universities.

SkillMap was developed as a demo-ready hackathon project and product concept. It demonstrates how career guidance, opportunity matching, employability intelligence, and academic planning can be brought together within one platform.

## Problem Statement

Career planning is often fragmented across separate tools.

Students may use one platform to explore courses, another to find internships, and another to assess their skills. Employers frequently struggle to evaluate candidates beyond keywords in a résumé, while universities may lack clear visibility into student career readiness and industry-aligned skill gaps.

SkillMap addresses these problems by creating a shared career intelligence ecosystem that helps:

* Candidates understand which careers fit their current profile.
* Students identify the skills needed for their target careers.
* Employers discover candidates based on explainable compatibility.
* Universities evaluate student readiness and programme alignment.
* Users move from career exploration to practical action.

## Target Users

SkillMap supports several user groups.

### Secondary School Students

Secondary school students can explore education and career pathways based on their interests, preferred subjects, and intended academic stream.

The workspace helps students understand the relationship between:

* Secondary school subjects
* Academic streams
* Pre-university pathways
* Degree programmes
* Career families
* Scholarship requirements
* Potential universities
* Future employment outcomes

### Higher Education Students

University and college students can evaluate career options based on their academic background, current skills, interests, and work preferences.

They can also:

* Discover internships and entry-level opportunities
* Review skill gaps
* Build career development roadmaps
* Track career readiness
* Access university-related academic insights
* Explore alumni and industry pathways

### Working Professionals

Working professionals can use SkillMap to assess career transitions, compare possible roles, identify transferable skills, and plan progression into more senior positions.

### Employers

Employers can create and manage job opportunities, review applicants, and evaluate candidate compatibility using explainable matching information.

### Universities

Higher education institutions can use aggregated student intelligence to understand employability readiness, programme outcomes, skill gaps, and industry alignment.

## Core Features

### Career Recommendation Engine

SkillMap evaluates a user’s profile and produces career recommendations based on several factors, including:

* Educational background
* Existing skills
* Personal interests
* Preferred work environment
* Experience level
* Career transition difficulty

Recommendations are presented with compatibility scores and supporting explanations so that users can understand why a career may or may not fit them.

### Explainable Compatibility Scoring

SkillMap is designed around career trajectory intelligence rather than absolute career prediction.

The scoring system considers multiple weighted dimensions:

| Dimension                  | Weight |
| -------------------------- | -----: |
| Degree or domain relevance |    25% |
| Skill compatibility        |    30% |
| Interest alignment         |    20% |
| Work-style alignment       |    15% |
| Transition feasibility     |    10% |

The resulting score is intended to support decision-making rather than guarantee career success.

### Skill-Gap Analysis

Users can compare their current profile against the expected requirements of a selected career.

The platform highlights:

* Existing strengths
* Transferable skills
* Missing technical skills
* Missing professional skills
* Priority development areas
* Recommended learning actions

### Personalised Career Roadmaps

SkillMap converts career recommendations into structured development roadmaps.

Roadmaps may include:

* Immediate next steps
* Skills to develop
* Suggested learning activities
* Education milestones
* Internship targets
* Entry-level roles
* Career progression stages
* Senior-role pathways
* Estimated salary progression

### Opportunity Discovery

Higher education students and working professionals can discover internships and jobs relevant to their profiles.

Opportunity cards may include:

* Job title
* Employer
* Location
* Employment type
* Monthly salary range
* Required skills
* Compatibility information
* Application status

Users can also save opportunities for later review.

### Candidate Career Hub

The Career Hub acts as a central workspace for a candidate’s career activity.

It may include:

* Saved opportunities
* Submitted applications
* Interview updates
* Career roadmap progress
* University workspace access
* Notifications
* Account and profile settings

### Employer Workspace

The employer workspace supports recruitment and candidate evaluation.

Key functions include:

* Job creation and management
* Candidate discovery
* Applicant review
* Candidate compatibility analysis
* Interview scheduling
* Application acceptance or rejection
* Recruitment notifications
* Employer insights

### Student University Workspace

Higher education candidates can access a university-focused workspace linked to their candidate account.

The workspace demonstrates features such as:

* Timetable management
* Semester information
* Academic progress
* Study and skill insights
* Career readiness
* Alumni discovery
* University progress tracking
* University email connection demo

### University Intelligence Workspace

The institutional university workspace provides a broader view of student and programme performance.

The workspace includes areas such as:

* Student intelligence
* Career readiness
* Skill-gap analysis
* Career and industry trends
* Programme insights
* Employability reporting
* Institutional reports

### Responsive Desktop and Mobile Experiences

SkillMap includes dedicated desktop and mobile interfaces.

Authenticated mobile experiences use a separate `/m/` route namespace:

```text
/m/candidate/...
/m/employer/...
/m/university/...
/m/auth/login
```

This separation prevents mobile users from being redirected into desktop-only interfaces and allows each workspace to use navigation designed for smaller screens.

## Platform Workspaces

### Candidate Workspace

The candidate experience changes depending on the user’s current stage.

#### Secondary School Navigation

```text
Discover
Pathways
Skill Gap
Roadmap
My Hub
```

#### Higher Education and Working Professional Navigation

```text
Discover
Opportunities
Skill Gap
Roadmap
Career Hub
```

### Employer Workspace

The desktop employer experience includes recruitment and talent intelligence capabilities.

The mobile employer experience focuses on operational actions such as:

```text
Interview Applications
Upcoming Interviews
Notifications
```

Administrative features such as job creation, talent-pool management, and analytics remain desktop-first.

### University Workspace

SkillMap separates the university experience into:

1. A student-facing university workspace accessed through the candidate account.
2. An institution-facing intelligence workspace for university representatives.

## Authentication and Role Management

SkillMap supports role-based access for:

* Candidates
* Employers
* Universities

The authentication flow is designed to preserve the user’s role, selected life stage, and intended destination.

Key behaviours include:

* Existing users are redirected to their appropriate workspace.
* New candidate users complete profile setup before receiving recommendations.
* Candidate stage information is persisted to the database.
* Signed-out users return to the landing page.
* Mobile users remain within the `/m/` namespace.
* Protected routes prevent users from accessing the wrong workspace.
* Sample profiles and quick-login options support evaluator demonstrations.

## User Journey

A typical candidate journey is:

1. Open the SkillMap landing page.
2. Select a current stage:

   * Secondary School
   * Higher Education
   * Working Professional
3. Create an account, sign in, or use a demonstration profile.
4. Complete the profile foundation.
5. Provide education, skills, interests, and work preferences.
6. Generate career recommendations.
7. Review compatibility scores and explanations.
8. Compare career options.
9. Inspect skill gaps.
10. Build a career roadmap.
11. Discover relevant opportunities.
12. Save opportunities or apply for interviews.
13. Track progress through the Career Hub.

## Technology Stack

### Frontend

* Next.js
* React
* TypeScript
* Tailwind CSS
* JavaScript
* Responsive component architecture

### Backend

* Next.js server-side functionality
* Server actions and API routes
* Supabase services

### Database and Authentication

* Supabase PostgreSQL
* Supabase Authentication
* Row-level security policies
* Role-based profile data

### Hosting and Deployment

* Vercel

### Development Tools

* Git
* GitHub
* Visual Studio Code
* npm
* Codex-assisted development workflows

## High-Level Architecture

```text
User Interface
│
├── Landing and Authentication
├── Candidate Workspace
├── Employer Workspace
├── University Workspace
└── Mobile Workspace
        │
        ▼
Application Layer
│
├── Route Protection
├── Role Management
├── Candidate Stage Management
├── Recommendation Engine
├── Opportunity Matching
├── Application Workflow
└── Notification Workflow
        │
        ▼
Data Layer
│
├── Supabase Authentication
├── Candidate Profiles
├── Employer Profiles
├── University Profiles
├── Career Data
├── Skill Data
├── Opportunities
├── Applications
└── Roadmap Progress
```

## Example Route Structure

The exact route structure may change as the prototype evolves, but the platform is generally organised around the following namespaces:

```text
/
├── auth/
│   ├── login
│   └── signup
├── candidate/
│   ├── discover
│   ├── opportunities
│   ├── skill-gap
│   ├── roadmap
│   └── careerhub
├── employer/
│   ├── jobs
│   ├── applicants
│   ├── talent-pool
│   ├── candidate-fit
│   ├── insights
│   └── updates
├── university/
│   ├── overview
│   ├── student-intelligence
│   ├── career-readiness
│   ├── skill-gaps
│   ├── programme-insights
│   ├── employability
│   └── reports
└── m/
    ├── auth/
    ├── candidate/
    ├── employer/
    └── university/
```

## Getting Started

### Prerequisites

Ensure the following software is installed:

* Node.js
* npm
* Git

### Installation

Clone the repository:

```bash
git clone <repository-url>
```

Enter the project directory:

```bash
cd <project-folder>
```

Install dependencies:

```bash
npm install
```

Create a local environment file:

```bash
cp .env.example .env.local
```

Add the required Supabase and application environment variables.

Example:

```env
NEXT_PUBLIC_SUPABASE_URL=your_supabase_project_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
SUPABASE_SERVICE_ROLE_KEY=your_service_role_key
NEXT_PUBLIC_APP_URL=http://localhost:3000
```

Do not commit private credentials or service-role keys to the repository.

Start the development server:

```bash
npm run dev
```

Open the application:

```text
http://localhost:3000
```

## Available Scripts

Common project scripts may include:

```bash
npm run dev
```

Runs the application in development mode.

```bash
npm run build
```

Creates a production build.

```bash
npm run start
```

Runs the production build locally.

```bash
npm run lint
```

Checks the project for linting issues.

The exact scripts should be verified against the project’s `package.json`.

## Demonstration Mode

SkillMap includes demonstration-oriented functionality intended to make evaluation easier.

Depending on the current build, demonstration features may include:

* Quick-login accounts
* Candidate sample profiles
* Employer sample accounts
* University sample accounts
* Pre-populated career recommendations
* Sample jobs and internships
* Example application statuses
* Sample university data
* Non-functional import or connection buttons for concept demonstration

Demo-only controls are clearly separated from production functionality where possible.

## Data and Scoring Disclaimer

SkillMap provides guidance based on the information available within the application.

Career compatibility scores should not be interpreted as:

* A guarantee of employment
* A psychological assessment
* A definitive measure of personal ability
* A replacement for professional career counselling
* A prediction of future success

The platform is intended to improve career exploration by making assumptions, strengths, gaps, and possible next steps more visible.

## Current Status

**Status:** Hackathon Prototype / Demo MVP

SkillMap currently demonstrates the core product experience, platform architecture, and career intelligence concept.

The project is not yet positioned as a production-ready recruitment or education platform.

Areas that would require further development before commercial deployment include:

* Expanded testing coverage
* Security auditing
* Production-grade monitoring
* More comprehensive datasets
* Recommendation-engine validation
* Accessibility auditing
* Performance optimisation
* Privacy and consent controls
* Institutional data integration
* Employer verification
* Real application and interview integrations

## Known Limitations

As a hackathon prototype, some features may use simulated or sample data.

Potential limitations include:

* Certain buttons may demonstrate intended behaviour without external API integration.
* Career recommendations depend on the completeness of the available dataset.
* Salary figures may be estimates or demonstration values.
* University information may not reflect live institutional systems.
* Job listings may be sample records.
* Employer and candidate workflows may not send real external communications.
* Some advanced analytics are presented as product concepts rather than fully validated models.
* Mobile and desktop features may differ intentionally.

## Future Development

Potential future improvements include:

* AI-assisted résumé generation
* Verified employer onboarding
* Live internship and job integrations
* University system integration
* Learning-platform integration
* Skills verification
* Portfolio and project assessment
* Interview preparation
* Mentor matching
* Career outcome tracking
* Labour-market trend analysis
* Real-time notification services
* Calendar-based interview scheduling
* Multilingual support
* Recommendation confidence indicators
* Administrative audit logs
* Expanded institutional reporting
* Mobile application development

## Project Objectives

SkillMap was built to demonstrate the following capabilities:

* Full-stack application development
* Multi-role platform architecture
* Responsive desktop and mobile design
* Authentication and route protection
* Database-driven user experiences
* Explainable scoring systems
* Career and education workflow design
* Employer-candidate platform linkage
* Product documentation
* Demo-ready commercial concept development

## Screenshots

Add product screenshots to a dedicated directory:

```text
/public/screenshots/
```

Recommended screenshots include:

* Landing page
* Candidate profile setup
* Career recommendation results
* Skill-gap analysis
* Career roadmap
* Candidate opportunities
* Career Hub
* Employer workspace
* Candidate-fit analysis
* Student university workspace
* University intelligence dashboard
* Mobile candidate interface

Example Markdown:

```md
![SkillMap Landing Page](./public/screenshots/landing-page.png)
```

## Live Demo

**Live Application:**
[Add SkillMap deployment URL]

**Demonstration Video:**
[Add walkthrough video URL]

**Detailed User Manual:**
[Add documentation URL or file path]

## Repository Documentation

Supporting documentation may include:

```text
README.md
DESIGN.md
demo-script.md
engine-map.md
function-inventory.md
page-route-map.md
supabase-map.md
types-map.md
data-flow-map.md
dependency-map.md
candidate-stage-architecture.md
DEMO_DATA_BOUNDARIES.md
auth-separation-testing.md
```

These documents provide further information about the platform’s architecture, routes, scoring system, database structure, demonstration boundaries, and testing approach.

## Author

**Ian Lee**

Computer Science Student
Full-Stack Developer and Product Builder

## Acknowledgements

SkillMap was developed as part of a hackathon project focused on improving career readiness, employability, education pathways, and talent matching.

The project combines product design, full-stack engineering, career intelligence, and multi-user platform architecture within a single prototype.

## Licence

Add the selected project licence here.

For example:

```text
MIT License
```

Before publishing the repository, confirm that the selected licence is appropriate for the project, datasets, third-party libraries, and hackathon submission requirements.
