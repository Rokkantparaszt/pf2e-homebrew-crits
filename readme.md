##Purpose##



Implement your homebrew PF2e crit rules and proficiency-based dice, while keeping normal PF2e workflows intact and making the chat card clearly show what happened.



Mechanics the module changes



Nat-crit behavior (d20 only)



Treat 17 as nat-20 and 3 as nat-1 for critical bump/demotion.



The ±1 DoS step from nat-20/nat-1 applies only to Untrained/Trained checks (never on Expert+).



Degree of Success threshold



Critical success/failure uses a ±5 margin vs DC (configurable), and the module can optionally write the computed DoS back to the message flags.



Proficiency die swap (optional, per-kind, PC-only toggle)



Expert → d16 + 4, Master → d12 + 8, Legendary → d10 + 10.



Untrained/Trained stay d20 (no offset).



Scope switches for skills / saves / perception / initiative / strikes (beta), plus a PCs-only gate.



These formulas are user-configurable in settings (e.g., “d12+11” for Master).



Concurrency-safe roll alteration



Die/offset changes are applied per roll instance (no global leakage), so “Roll to All” initiatives respect each combatant’s rank and the PCs-only gate.



What you’ll see in chat (UI tweaks)



Clean, truthful formula:



Rewrites the card’s line to show: 1dX(natural) + offset + modifier.



The offset is highlighted (turquoise) so players see what the proficiency grants.



Nat-crit coloring only when it really is:



No red/green when there’s no DC.



The big total number turns red/green only on real nat-crits by your rules (U/T d20: 3↓ / 17↑). A plain 20 is not auto-green.



Compact banner:



Shows dX roll: N (+ “(Crit)” tag when applicable) and the DoS line (Success/Failure/Crit by N).



Proficiency chip fix:



If PF2e’s chip text lags, it’s corrected to the true rank (e.g., Expert +4).



Controls \& compatibility



Settings:



Toggle die swap per check type; PCs-only; ±5 DoS; nat-crit values; and per-rank formulas (dX+N).



Settings panel shows a live summary of the current formulas.



Diagnostics (optional):



Discovery Mode: logs PF2e context/DoS flow.



Trace Dice: traces formula → terms → evaluate (for debugging only).



Foundry/PF2e compatibility:



Uses renderChatMessageHTML (V13-safe).



Uses libWrapper string-target registration.



No deprecated hooks; no mutation of other modules.



In short: the module swaps dice by proficiency, applies your nat-crit \& ±5 rules correctly, makes the chat card transparently show die(nat) + offset + mod, and stays robust (including “Roll to All”) without breaking PF2e’s core flow.


