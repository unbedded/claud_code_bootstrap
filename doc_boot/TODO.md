# TODO - Template Improvements

## Current State

**Commands Strategy:**
- **Master Source:** `recipe_binder/.claude/commands/` (simple, working well)
- **Bootstrap Template:** Will sync from recipe_binder for consistency
- Commands are concise (480 lines total vs bootstrap's 1952 lines)
- Direct wrappers without extensive documentation

**What Works Well in Recipe_binder:**
- ✅ Simple, focused command files (20-30 lines each)
- ✅ Clear examples without verbose explanations
- ✅ Minimal markdown formatting overhead
- ✅ Easy to scan and understand quickly

**Bootstrap Advantages (Future Enhancement):**
- Comprehensive safety validations (pre-flight checks)
- Educational content (teaches git-flow concepts)
- Advanced features (health-check-git, release-doctor)
- Quality gates integrated into git-flow
- Template system for language-specific CLAUDE.md

---

## Phase 1: Safety Enhancement (Future)

**Goal:** Add comprehensive safety features to simple recipe_binder-style commands

**Tasks:**
1. [ ] Add pre-flight validation to gitflow-start
   - Working tree check (no uncommitted changes)
   - Branch verification (starting from correct branch)
   - Sync status check (up-to-date with remote)
   - Duplicate branch prevention

2. [ ] Add quality gates to gitflow-finish
   - Run `make quality` before merge
   - Run `make test-full` for releases/hotfixes
   - Verify clean working tree

3. [ ] Add new safety commands
   - `/health-check-git` - Repository diagnostics with auto-fix
   - `/release-doctor` - AI-powered git-flow problem recovery
   - Enhanced `/release-finish` - Production deployment safety

4. [ ] Keep command files concise
   - Document safety features inline with minimal text
   - Use comments for implementation details
   - Preserve recipe_binder's readability

**Deliverables:**
- All safety validations from bootstrap
- Commands stay under 40 lines each
- No loss of simplicity or clarity

---

## Phase 2: Documentation & Education (Future)

**Goal:** Add educational value without cluttering command files

**Tasks:**
1. [ ] Create `.claude/COMMANDS-GUIDE.md`
   - Detailed git-flow concepts and best practices
   - Educational content on why each safety check matters
   - Error recovery procedures and troubleshooting
   - Examples of common workflows

2. [ ] Create `.claude/ARCHITECTURE.md`
   - Explain Makefile abstraction layer
   - Language-agnostic design principles
   - Template system documentation
   - How commands work together

3. [ ] Add inline documentation comments
   - Keep command headers minimal (recipe_binder style)
   - Move verbose explanations to implementation comments
   - Link to COMMANDS-GUIDE.md for detailed learning

4. [ ] Update README-ENV.md
   - Reference new documentation files
   - Add "Learning Path" section
   - Link commands to educational content

**Deliverables:**
- Comprehensive learning resources separate from command files
- Command files remain simple and maintainable
- Users can choose depth: quick reference vs deep learning

---

## Phase 3: Feature Parity & Optimization (Future)

**Goal:** Bring useful features from old commands without tool-specific coupling

**Tasks:**
1. [ ] Review deprecated commands for useful patterns
   - `check-code --report` → Add to `make quality`?
   - `run-tests --filter <pattern>` → Add to `make test`?
   - `run-tests --parallel` → Configure in pytest by default?

2. [ ] Enhance Makefile targets
   - Add `make quality-report` for detailed output
   - Add `make test-filter PATTERN=<pattern>` for selective tests
   - Add `make test-parallel` for parallel execution

3. [ ] Template improvements
   - Ensure CLAUDE-python.md and CLAUDE-cpp.md are comprehensive
   - Add examples for mixed-language projects
   - Document template customization

4. [ ] Cleanup and standardization
   - Remove all old/deprecated commands from recipe_binder
   - Sync both projects to same command structure
   - Verify all commands work across Python/C++ projects

**Deliverables:**
- Best features from old commands preserved
- Tool abstraction maintained (no /check-code, /run-tests)
- Both projects fully synchronized

---

## Current Priorities (Not in TODO phases above)

**Immediate Actions Completed:**
- ✅ Updated CLAUDE.md line-length to 120
- ✅ Created clean VERSION and CHANGELOG.md templates in root
- ✅ Compared pyproject.toml files
- ✅ Analyzed .claude directory differences
- ✅ Identified recipe_binder as master for commands

**Next Steps:**
- ✅ Copied recipe_binder simple gitflow commands to bootstrap
- ✅ Kept bootstrap's advanced commands (health-check-git, release-doctor, etc.)
- ✅ Kept bootstrap's superior version-bump (language-agnostic) over recipe_binder's bump-version
- ✅ Bootstrap's release-start already includes plan-release functionality
- [ ] Test all commands work in bootstrap template
- [ ] Sync bootstrap commands back to recipe_binder (standardize both projects)
- [ ] Clean up recipe_binder deprecated commands (see below)

**Recipe_binder Cleanup Needed:**
Commands to REMOVE from recipe_binder (deprecated/replaced by Makefile):
- ❌ analyze-changes.md (old - marked for removal per README)
- ❌ check-code.md (old - replaced by `make quality`)
- ❌ review-code.md (old - marked for removal)
- ❌ review-commits.md (old - marked for removal)
- ❌ run-tests.md (old - replaced by `make test` / `make test-full`)
- ❌ suggest-version.md (old - marked for removal)
- ❌ bump-version.md (replace with bootstrap's language-agnostic version-bump.md)
- ❌ plan-release.md (functionality integrated into release-start.md)

Commands to ADD to recipe_binder from bootstrap:
- ✅ health-check-git.md (repository diagnostics)
- ✅ makefile-generate.md (language-agnostic build system)
- ✅ release-doctor.md (AI-powered git-flow recovery)
- ✅ release-finish.md (production release completion)
- ✅ release-start.md (AI planning + branch creation, replaces plan-release.md)
- ✅ version-bump.md (replaces bump-version.md with language-agnostic version)

---

## Decision Log

**2025-10-03: Command Strategy**
- Recipe_binder commands adopted as master (simple, proven, working)
- Bootstrap's verbose documentation style deferred to Phase 2
- Safety features from bootstrap deferred to Phase 1
- Focus on simplicity and maintainability first

**Key Insight:**
> "The recipe_binder works very well - and it should be our master"
>
> Simpler is better. Add complexity intentionally in future phases when value is clear.

---

## Notes

- Commands directory is the only area needing sync
- Both projects have identical tools/, templates/, settings.json
- Future phases are optional enhancements, not blockers
- Template is production-ready with simple commands from recipe_binder
