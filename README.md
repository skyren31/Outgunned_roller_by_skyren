# 🎲 Outgunned Dice Roller (v1.0 beta)

This is an automated **Dice Roller** alias for Avrae Discord, tailor-made for the **Outgunned RPG** system. Unlike traditional RPG rollers, this bot calculates your score based on the **highest frequency of matching dice (pairs/sets)** rather than adding up the face values. It also features built-in mechanics for risk management and re-rolls.

---

## 🚀 How to Use (Commands)

### 1. Initial Roll
Rolls your starting dice pool (hard-capped between a minimum of 2 and a maximum of 9 dice). Supports simple arithmetic calculations (`+` and `-`).
* **Format:** `!og [number of dice]`
* **Examples:** 
  * `!og 5` (Rolls 5 dice)
  * `!og 4+2` (Automatically calculates and rolls 6 dice)
  * `!og 0` (Automatically rounds up to the hard minimum of **2 dice**)

### 2. Standard Re-roll (`r`)
Re-rolls the remaining dice that did not match. You **must** have at least a *Basic Success* (2 matching dice) as a baseline.
* **Risk:** If the new roll fails to improve your set, your initial success level is penalized by -1.
* **Format:** `!og [remaining dice] r [saved face] [initial matching count]`
* **Example:** `!og 3 r 4 2` (Re-rolls 3 dice, while keeping a pair of **4**s).

### 3. Free Re-roll (`f`)
A special re-roll granted by specific character Feats or gear. Can be used even if the initial roll completely failed (0 successes) and carries **no penalty risk**.
* **Format:** `!og [remaining dice] f [saved face] [initial matching count]`
* **Example:** `!og 5 f 0 0` (Free re-roll for 5 dice from a complete failure).

### 4. All In (`a`)
A high-stakes gamble accessible only after a successful re-roll has already improved your score.
* **Extreme Risk:** If the All In roll fails to improve your set further, **all accumulated successes are instantly lost (wiped to 0 / Failure)**.
* **Format:** `!og [remaining dice] a [saved face] [initial matching count]`
* **Example:** `!og 1 a 5 4` (Goes All In using the last 1 remaining die).

---

## 🏆 The Success Ladder
Your final result is automatically evaluated based on your highest matching set:
* **0 - 1 Match:** `Failure` 🔴
* **2 Matching Dice:** `Basic Success` 🟠
* **3 Matching Dice:** `Critical Success` 🟡
* **4 Matching Dice:** `Extreme Success` 🟢
* **5 Matching Dice:** `Impossible Success` 🔵
* **6+ Matching Dice:** `Jackpot!!!` 🟣

*Note: The Discord embed border color changes dynamically to visually match your current success level!*
