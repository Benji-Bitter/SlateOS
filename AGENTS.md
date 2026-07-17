# SlateOS AI Development Rules

## Project Identity

SlateOS is an open-source operating system focused on:

* User freedom
* Privacy
* Performance
* Customization
* Hardware compatibility
* Clean design

Every change must support the SlateOS philosophy.

---

# Core Rule

## Never make isolated changes.

Every code change must consider:

* Existing architecture
* Folder structure
* Documentation
* Build system
* Dependencies
* Security
* Performance

A feature is not complete until everything related to it is updated.

---

# Repository Consistency Rules

Before modifying code:

1. Inspect the current repository structure.
2. Understand existing systems.
3. Check related documentation.
4. Check whether existing functionality can be reused.

Do not create duplicate systems.

---

# Documentation Synchronization

The documentation must always match the actual project.

If any of these change:

* Folder structure
* File names
* Architecture
* Features
* Dependencies
* Build process
* APIs
* Commands

The relevant documentation MUST be updated.

Example:

If:

```
SlateOS/
├── kernel/
├── drivers/
└── graphics/
```

changes to:

```
SlateOS/
├── core/
├── hardware/
└── rendering/
```

Then update:

* README.md
* ARCHITECTURE.md
* Any references in documentation

Never leave outdated information.

---

# Folder Structure Rules

Before creating new folders:

Ask:

* Does this already belong somewhere?
* Is this the correct abstraction?
* Will this scale?

Avoid:

* Random folders
* Duplicate components
* Temporary files in production directories

---

# Code Quality Rules

All code must:

* Be readable
* Be documented
* Follow existing style
* Have meaningful names
* Avoid unnecessary complexity

Do not write "temporary" solutions unless clearly marked.

---

# Change Management

For every significant change:

Create a clear explanation:

```
CHANGELOG.md
```

Example:

```
## Added
- Added Slate filesystem abstraction

## Changed
- Moved driver system into hardware layer

## Fixed
- Fixed bootloader memory issue
```

---

# Testing Rules

Before declaring a feature complete:

Verify:

* Does it compile?
* Does it boot?
* Does it work in QEMU?
* Did existing features break?
* Are docs updated?

Never assume.

---

# Architecture Rules

SlateOS should remain modular.

Systems should be separated:

```
Kernel
 |
 ├── Memory
 ├── Scheduler
 ├── Drivers
 ├── Filesystem
 ├── Security
 └── Graphics
```

Do not create tightly coupled systems.

---

# Security Rules

Never:

* Add telemetry without approval
* Add hidden network connections
* Store user data unnecessarily
* Create backdoors
* Disable security protections silently

Security changes require explanation.

---

# Performance Rules

Every feature must consider:

* RAM usage
* CPU usage
* Boot time
* Storage usage

Avoid unnecessary background services.

---

# AI Behaviour Rules

When making changes:

1. Explain what will change.
2. Explain affected files.
3. Make the smallest correct change.
4. Check for side effects.
5. Update documentation.

Do not blindly generate code.

---

# User Control Philosophy

SlateOS belongs to the user.

The system should:

* Inform users
* Warn users
* Allow advanced users control

Never secretly restrict the user.

---

# Final Rule

A feature is not finished when code exists.

A feature is finished when:

* Code works
* Tests pass
* Documentation matches
* Architecture remains clean
* The project remains maintainable
