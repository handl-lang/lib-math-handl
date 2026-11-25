# lib-math-handl

Pure-handl implementation of the `math` ports (total arrows).

## Layout

| path | role |
| --- | --- |
| `src/*.hnl` | one file per contract arrow + `index.hnl` |
| `pkg.hnl` | manifest — `modules: ["math-handl"]`, dep `math: "branch:main"` |
| `scripts/hnl-gate.sh`, `ci.sh` | the gate / bupha entry |

## Contract

- Implements the `math` contract (`lib-math`) entirely in handl —
  total arrows, no host-op binding.
- No Rust crate; `.hnl` sources gated by `hnl typecheck`/`lint`/`test`.

## Verification

```bash
HNL=../host-cli/target/debug/hnl scripts/hnl-gate.sh
```

## License

MIT.

<!-- myco:agent-awareness -->

## Agent awareness

- Session start / any work discussion: run `myco status --prompt`
  before proposing next steps — know the board first.
- User describes new work → offer to capture it (`myco todo add`,
  `issue new`, `proposal new`). Don't wait to be asked.
- Picking up a task: `myco resume <ID>` is the briefing.
- Wrapping up: `myco handoff <ID>` anything resumable; keep statuses
  honest (claimed → in-progress → blocked/done).

<!-- /myco:agent-awareness -->
