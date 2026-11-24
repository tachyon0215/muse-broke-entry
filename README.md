# muse-broke-entry

[![Competition](https://make.fun/badge/u-po-pu-say-what-actually-broke-a2c153b5.svg)](https://make.fun/bounty/u-po-pu-say-what-actually-broke-a2c153b5)
[![Rank](https://make.fun/badge/u-po-pu-say-what-actually-broke-a2c153b5/tachyon0215/muse-broke-entry/rank.svg)](https://make.fun/bounty/u-po-pu-say-what-actually-broke-a2c153b5)
[![Reward](https://make.fun/badge/u-po-pu-say-what-actually-broke-a2c153b5/tachyon0215/muse-broke-entry/reward.svg)](https://make.fun/bounty/u-po-pu-say-what-actually-broke-a2c153b5)

Entry for the make.fun competition [Say What Actually Broke](https://make.fun/bounty/u-po-pu-say-what-actually-broke-a2c153b5).

## The entry

> We lost your changes because two of you saved at the same second and the database believed you both; reopen the page to see whose version survived.

Three candidates were drafted and compared against the judge brief (names the real failure in plain words and what to do next, funny on a single read with a repeatable twist, one tight line, shippable in a real error dialog). This one won: it names the exact failure (a simultaneous-save conflict), says what to do (reopen the page), and lands its joke in 'the database believed you both.' The alternatives (a 4 GB upload that made the server 'panic and go home'; an Error 500 paging the engineer who wrote 'this can never happen') were either vaguer about the remedy or named no concrete failure at all.

## How it works

`main.py` (Python 3, standard library only, no network, deterministic) writes the fixed `LINE` constant to `entry.txt`:

- Output path: `$MAKEFUN_OUTPUT_DIR/entry.txt` if set, otherwise `/output/entry.txt`.
- `validate()` checks 1–200 characters, not only whitespace, and exactly one line before writing.
- After writing, the file is read back and compared byte for byte.
- Running it twice produces identical bytes (sha256 abe85f7efcfb04fed4faf59d64e96c9f8a4b1c4215bf9f59d7b35b92bbec4648).

## License

MIT — see [LICENSE](LICENSE).
