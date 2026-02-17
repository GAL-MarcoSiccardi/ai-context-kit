# Command Reference Template

Use this table shape inside the generated project instructions.

| Command | Parameters | Description | Example |
| --- | --- | --- | --- |
| `/tag.context` | - | Display current session state | `/ack.context` |
| `/tag.mode [role]` | role names | Switch assistant role | `/ack.mode developer` |
| `/tag.phase [name]` | phase names | Update work phase | `/ack.phase testing` |
| `/tag.style [type]` | `structured` \\| `minimal` \\| `detailed` \\| `annotated` | Change output verbosity | `/ack.style minimal` |
| `/tag.tone [style]` | `technical` \\| `direct` \\| `detailed` \\| `concise` | Adjust communication tone | `/ack.tone concise` |
| `/tag.interact [mode]` | `advisory` \\| `pair` \\| `driver` | Set collaboration style | `/ack.interact pair` |
| `/tag.reset` | - | Reset session state | `/ack.reset` |
