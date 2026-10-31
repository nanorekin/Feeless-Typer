# Feeless Typer

A free, single-file browser typing game with Nano at its heart. Crypto and Nano words fall from the top of the board; type them before they reach the bottom. No build step, no backend, no fees.

## Play

- **Type** a word's first letter to lock onto it (closest to the bottom wins if several share a letter), then keep typing to destroy it. Tap the board to bring up your keyboard — there's no text box to aim at.
- **Daily challenge:** the same 20 words in the same order for everyone, new every day at 00:00 UTC. Clear all 20 without running out of lives to mark the day cleared and keep your streak.
- **Quick 60:** a free-for-all for 60 seconds. Words fall a little faster as the clock runs down.
- **Survival:** endless. Words keep speeding up; game over at 0 lives.
- **Lives:** 3 to start (4 for supporters). A word reaching the bottom costs a life and resets your combo; a wrong letter while locked onto a word also resets the combo, but the word stays — just try the next correct letter.
- **Scoring:** roughly twice a word's length, boosted by your current combo streak.
- **Ranks** (by total words typed correctly): Newbie, Hodler (150), Diamond Hands (500), Whale (1,500), Satoshi (4,000).
- Each round ends with words per minute (WPM) and accuracy, and a share message.

Everything is stored in the player's browser. Works with a physical keyboard or a phone's on-screen keyboard.

## Editing the word bank

Words live near the top of the script in `index.html`, split into three arrays by difficulty: `SHORT`, `MEDIUM` and `HARD` (the last holding short phrases). Keep entries lowercase letters and spaces only.

## Deploy on GitHub Pages

1. Create a new repository, for example `feeless-typer`.
2. Upload `index.html` and `README.md` to the root of the repository.
3. Open **Settings > Pages**, set the source to **Deploy from a branch**, choose `main` and `/ (root)`, then save.
4. After a minute the game is live at `https://<your-username>.github.io/feeless-typer/`.

## Donations

The tip card works the same way as in the other Feeless games:

- A `nano:` payment link with the chosen amount, shown as a QR code and an **Open in wallet** button.
- A **Copy address** button.
- An **I've sent it, check** button that asks public Nano nodes whether a matching payment arrived, and unlocks the supporter perks (Gold, Mint and Neon accent colours, and a 4th life) on that browser.

To use a different wallet, change `NANO_ADDRESS` near the top of the script in `index.html`. If the public RPC endpoints in `RPCS` ever block browser requests, point them at your own proxy.

The supporter unlock is stored in `localStorage`, so it is a thank-you perk, not secure access control.

Add `?selftest` to the URL to expose a small `window.__nt` object for automated tests.
