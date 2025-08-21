---
description: Analyze Current Product & Install Agent OS
globs:
alwaysApply: false
version: 1.0
encoding: UTF-8
---

# Analyze Current Product & Install Agent OS

## Overview

Install Agent OS into an existing codebase, analyze current product state and progress.  Builds on plan-product.md

<pre_flight_check>
  EXECUTE: @~/.agent-os/instructions/meta/pre-flight.md
  NOTE: Path conventions — Home: @~/.agent-os, Project: @.agent-os
  WEB_SEARCH_CHECK:
    IF uncertain OR current info required:
      USE: @Web to fetch latest official docs/best practices (never curl)
  MCP_CONTEXT7_CHECK:
    WHEN: docs/api/library/examples/usage are needed OR library usage/version is uncertain
    USE: Context7 (resolve-library-id → get-library-docs) to fetch authoritative docs
  SEQUENTIAL_THINKING:
    ACTION: Use sequential-thinking MCP to structure the analysis plan and verification steps
  STANDARDS_INDEX_CHECK: If unsure which standard to consult, READ @~/.agent-os/standards/README.md to pick targets
</pre_flight_check>

<process_flow>

<step number="1" name="analyze_existing_codebase">

### Step 1: Analyze Existing Codebase

Perform a deep codebase analysis of the current codebase to understand current state before documentation purposes.

<analysis_areas>
  <project_structure>
    - Directory organization
    - File naming patterns
    - Module structure
    - Build configuration
  </project_structure>
  <technology_stack>
    - Frameworks in use
    - Dependencies (package.json, Gemfile, requirements.txt, etc.)
    - Database systems
    - Infrastructure configuration
  </technology_stack>
  <implementation_progress>
    - Completed features
    - Work in progress
    - Authentication/authorization state
    - API endpoints
    - Database schema
  </implementation_progress>
  <code_patterns>
    - Coding style in use
    - Naming conventions
    - File organization patterns
    - Testing approach
  </code_patterns>
</analysis_areas>

<instructions>
  ACTION: Thoroughly analyze the existing codebase
  DOCUMENT: Current technologies, features, and patterns
  IDENTIFY: Architectural decisions already made
  NOTE: Development progress and completed work
</instructions>

</step>

<step number="2" subagent="context-fetcher" name="gather_product_context">

### Step 2: Gather Product Context

Use the context-fetcher subagent to supplement codebase analysis with business context and future plans.

<context_questions>
  Based on my analysis of your codebase, I can see you're building [OBSERVED_PRODUCT_TYPE].

  To properly set up Agent OS, I need to understand:

  1. **Product Vision**: What problem does this solve? Who are the target users?

  2. **Current State**: Are there features I should know about that aren't obvious from the code?

  3. **Roadmap**: What features are planned next? Any major refactoring planned?

  4. **Decisions**: Are there important technical or product decisions I should document?

  5. **Team Preferences**: Any coding standards or practices the team follows that I should capture?
</context_questions>

<instructions>
  ACTION: Ask user for product context
  COMBINE: Merge user input with codebase analysis
  PREPARE: Information for plan-product.md execution
</instructions>

</step>

<step number="3" name="execute_plan_product">

### Step 3: Execute Plan-Product with Context

Execute our standard flow for installing Agent OS in existing products

<execution_parameters>
  <main_idea>[DERIVED_FROM_ANALYSIS_AND_USER_INPUT]</main_idea>
  <key_features>[IDENTIFIED_IMPLEMENTED_AND_PLANNED_FEATURES]</key_features>
  <target_users>[FROM_USER_CONTEXT]</target_users>
  <tech_stack>[DETECTED_FROM_CODEBASE]</tech_stack>
</execution_parameters>

<execution_prompt>
  @~/.agent-os/instructions/core/plan-product.md

  I'm installing Agent OS into an existing product. Here's what I've gathered:

  **Main Idea**: [SUMMARY_FROM_ANALYSIS_AND_CONTEXT]

  **Key Features**:
  - Already Implemented: [LIST_FROM_ANALYSIS]
  - Planned: [LIST_FROM_USER]

  **Target Users**: [FROM_USER_RESPONSE]

  **Tech Stack**: [DETECTED_STACK_WITH_VERSIONS]
</execution_prompt>

<instructions>
  ACTION: Execute plan-product.md with gathered information
  PROVIDE: All context as structured input
  ALLOW: plan-product.md to create .agent-os/product/ structure
</instructions>

</step>

<step number="4" name="function_analysis_and_documentation">

### Step 4: Product Documentation Refinement

Refine product documentation to reflect the current codebase without generating technical inventories or census files.

<refinement_areas>
  <roadmap_alignment>
    - Map implemented features to roadmap items
    - Identify gaps between codebase and roadmap
    - Adjust roadmap phases as needed
  </roadmap_alignment>
  <tech_stack_accuracy>
    - Verify detected technologies and versions
    - Note deviations from defaults or standards
  </tech_stack_accuracy>
  <decisions_capture>
    - Capture key architectural or product decisions discovered during analysis
    - Add concise rationale and consequences
  </decisions_capture>
</refinement_areas>

<execution_instructions>
  ACTION: Update product docs (roadmap, tech-stack, decisions) only
  SKIP: Function inventory, dependency analysis, and variable census
  VERIFY: Documentation accurately reflects current implementation
</execution_instructions>

<output_requirements>
  - Roadmap updated to reflect completed and planned work
  - Tech stack verified and corrected as needed
  - Decisions log updated with key findings
  - Summary of any critical issues or risks
</output_requirements>

</step>

<step number="5" name="customize_generated_files">

### Step 5: Customize Generated Documentation

Refine the generated documentation to ensure accuracy for the existing product by updating roadmap, tech stack, and decisions based on actual implementation.

<customization_tasks>
  <roadmap_adjustment>
    - Mark completed features as done
    - Move implemented items to "Phase 0: Already Completed"
    - Adjust future phases based on actual progress
  </roadmap_adjustment>
  <tech_stack_verification>
    - Verify detected versions are correct
    - Add any missing infrastructure details
    - Document actual deployment setup
  </tech_stack_verification>
  <decisions_documentation>
    - Add historical decisions that shaped current architecture
    - Document why certain technologies were chosen
    - Capture any pivots or major changes
  </decisions_documentation>
</customization_tasks>

<roadmap_template>
  ## Phase 0: Already Completed

  The following features have been implemented:

  - [x] [FEATURE_1] - [DESCRIPTION_FROM_CODE]
  - [x] [FEATURE_2] - [DESCRIPTION_FROM_CODE]
  - [x] [FEATURE_3] - [DESCRIPTION_FROM_CODE]

  ## Phase 1: Current Development

  - [ ] [IN_PROGRESS_FEATURE] - [DESCRIPTION]

  [CONTINUE_WITH_STANDARD_PHASES]
</roadmap_template>


</step>

<step number="6" name="final_verification">

### Step 6: Final Verification and Summary

Verify installation completeness and provide clear next steps for the user to start using Agent OS with their existing codebase.

<verification_checklist>
  - [ ] .agent-os/product/ directory created
  - [ ] All product documentation reflects actual codebase
  - [ ] Roadmap shows completed and planned features accurately
  - [ ] Tech stack matches installed dependencies
  - [ ] Product documentation refined to match codebase
</verification_checklist>

<summary_template>
  ## ✅ Agent OS Successfully Installed

  I've analyzed your [PRODUCT_TYPE] codebase and set up Agent OS with documentation that reflects your actual implementation.

  ### What I Found

  - **Tech Stack**: [SUMMARY_OF_DETECTED_STACK]
  - **Completed Features**: [COUNT] features already implemented
  - **Code Style**: [DETECTED_PATTERNS]
  - **Current Phase**: [IDENTIFIED_DEVELOPMENT_STAGE]

  ### What Was Created

  - ✓ Product documentation in `.agent-os/product/`
  - ✓ Roadmap with completed work in Phase 0
  - ✓ Tech stack reflecting actual dependencies
  - ✓ Product docs aligned with codebase

  ### Next Steps

  1. Review the generated documentation in `.agent-os/product/`
  2. Make any necessary adjustments to reflect your vision
  3. See the Agent OS README for usage instructions: https://github.com/buildermethods/agent-os
  4. Start using Agent OS for your next feature:
     ```
     @~/.agent-os/instructions/core/create-spec.md
     ```

  Your codebase is now Agent OS-enabled! 🚀
</summary_template>


</step>

</process_flow>

## Error Handling

<error_scenarios>
  <scenario name="no_clear_structure">
    <condition>Cannot determine project type or structure</condition>
    <action>Ask user for clarification about project</action>
  </scenario>
  <scenario name="conflicting_patterns">
    <condition>Multiple coding styles detected</condition>
    <action>Ask user which pattern to document</action>
  </scenario>
  <scenario name="missing_dependencies">
    <condition>Cannot determine full tech stack</condition>
    <action>List detected technologies and ask for missing pieces</action>
  </scenario>
</error_scenarios>

## Execution Summary

<final_checklist>
  <verify>
    - [ ] Codebase analyzed thoroughly
    - [ ] User context gathered
    - [ ] plan-product.md executed with proper context
    - [ ] Product documentation refined to match codebase
    - [ ] Documentation customized for existing product
    - [ ] Team can adopt Agent OS workflow
  </verify>
</final_checklist>

<todo_list_standards>
  **Todo List Format Standards:**
  - **Incomplete tasks**: `- [ ] Task description`
  - **Completed tasks**: `- [x] Task description` 
  - **Never use**: `- [ ] Task description ✅ **COMPLETED**`
  - **Update immediately**: Change `[ ]` to `[x]` when task is done
  - **Keep clean**: No completion text inside checkboxes
</todo_list_standards>

<todo_list_guidelines>
  **Todo List Guidelines:**
  - **Use for tracking**: Development progress, implementation steps, testing phases
  - **Update promptly**: Mark tasks complete as soon as they're done
  - **Be specific**: Use clear, actionable task descriptions
  - **Group logically**: Organize related tasks together
  - **Include context**: Add relevant details for complex tasks
</todo_list_guidelines>
