# Browser policy

`static-policy.json` is the browser-native actor exported from a
`bang_structured_v2` checkpoint at iteration 2861 (run `mmd_v2_a030_s2`). It was
trained with the standard v2 League PPO recipe plus a Magnetic Mirror Descent
term (alpha 0.3, magnet moved every 50 updates), and replaces the iteration-2995
PPO champion. Keeping the inference artifact in the repository makes the
production build reproducible in GitHub Actions without granting CI access to
local training runs.

Regenerate it from a complete checkpoint with:

```sh
python3 tools/export_static_policy.py \
  runs/mmd_v2_a030_s2/champion/policy.pt \
  policy/static-policy.json
```
