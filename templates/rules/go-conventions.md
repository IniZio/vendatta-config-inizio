---
title: Go Conventions
description: Standardized Go coding style for Vendatta
globs: ["**/*.go"]
---

# GO CONVENTIONS

- Go 1.24+ features preferred.
- Use `fmt.Errorf("...: %w", err)` for error wrapping.
- Table-driven tests are encouraged.
- Follow `internal/` package pattern for private logic.
- Avoid `interface{}` where possible; use Generics or specific interfaces.
