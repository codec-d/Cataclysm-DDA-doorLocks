<!-- HOW TO USE: Under each "#### Heading" below, enter information relevant to your pull request.
Leave the headings unless they don't apply to your PR.

Please read carefully and don't delete the comments delimited by "< !--" and "-- >"
Once a pull request is submitted, automatic stylistic and consistency checks will be performed on the PR's changes.
The results of these can be either seen under the "Files changed" section of a PR or in the check's details.

NOTE: Please grant permission for repository maintainers to edit your PR.  It is EXTREMELY common for PRs to be held up due to trivial changes being requested and the author being unavailable to make them. -->

#### Summary
Features "Adding door locks and associated mechanics"
<!-- This section should consist of exactly one line, edit the one above.
1. Replace the word "Category" with one of these words: Features, Content, Interface, Mods, Balance, Bugfixes, Performance, Infrastructure, Build, I18N.
2. Replace the text inside the quotes with a brief description of your changes.
Or if you don't want a changelog entry, replace the whole line with just the word "None" (with no quotes).
For more on the meaning of each category, see:
https://github.com/CleverRaven/Cataclysm-DDA/blob/master/doc/CHANGELOG_GUIDELINES.md
If approved and merged, your summary will be added to the project changelog:
https://github.com/CleverRaven/Cataclysm-DDA/blob/master/data/changelog.txt -->

#### Purpose of change
The purpose of this change is to introduce a door locking mechanic.
This mechanic allows players to secure doors using locks and keys, providing an additional layer of strategy and resource management.
Moreover, this change aims to improve the realism and immersion by making NPCs and certain monsters interact with locked doors intelligently, either by attempting to pick the lock, breaking it down, or bypassing it altogether.
This modification encourages players to adapt their tactics and offers new opportunities for exploration and decision-making in the game world.
<!-- With a few sentences, describe your reasons for making this change.  If it relates to an existing issue, you can link it with a # followed by the GitHub issue number, like #1234.  If your pull request *fully* resolves an issue, include the word "Fix" or "Fixes" before the issue number, like: Fixes #xxxx
If there is no related issue, explain here what issue, feature, or other concern you are addressing.  If this is a bugfix, include steps to reproduce the original bug, so your fix can be verified. -->

#### Describe the solution
The door locking mechanic is implemented by modifying door entities to support locks and keys, adding lock/unlock actions, and updating AI behavior for various in-game entities.
Door locks and keys are defined as new item types in JSON, and doors have a new field to store lock information.
Locking and unlocking actions are added to the action handling code, checking for the corresponding key in the player's inventory.
AI behavior for portal storm monsters is adjusted to attempt opening locked doors without breaking them, while other entities may break down locked doors or attempt lockpicking if they possess the necessary skill and tools.
Lockpicking mechanics are implemented, allowing players and NPCs with sufficient skill to unlock locked doors.

the proposed solution of implementing a door locking mechanic with separate door locks and keys, along with lockpicking mechanics and updated AI behavior, was chosen as it offers a good balance of realism, strategic depth, and integration with the existing game systems.
<!-- How does the feature work, or how does this fix a bug?  The easier you make your solution to understand, the faster it can get merged. -->

#### Describe alternatives you've considered
Keyless locking mechanisms: One alternative considered was implementing a keyless locking mechanism, such as combination locks or electronic locks.
While these could add more variety to the game, they would require additional user interfaces and interactions that may complicate the gameplay experience.
The key-based system is more straightforward and easier to integrate with the existing game mechanics.

Simplified lock interactions: Another approach was to simplify the door locking mechanic by allowing players to lock and unlock doors without keys, using only their lockpicking skill.
However, this would reduce the strategic depth and realism of the feature.
By introducing keys and lockpicking mechanics, players must manage their inventory and make decisions based on the risks and rewards of accessing locked areas.

Doors with built-in locks: Instead of adding separate door lock items, we could modify existing door entities to include a built-in lock with a chance to be locked.
This would simplify the implementation, but it would remove the possibility for players to add or remove locks from doors, reducing the customization and interaction options available in the game.
<!-- Explain any alternative solutions, different approaches, or possibilities you've considered using to solve the same problem. -->

#### Testing

<!-- Describe what steps you took to test that this PR resolved the bug or added the feature, and what tests you performed to make sure it didn't cause any regressions.  Also include testing suggestions for reviewers and maintainers. -->

#### Additional context
A potential gameplay scenario to help illustrate how the door locking mechanic would work in practice:
1. A player comes across a locked door in a building.
The door has a lock icon on it, indicating its locked status. The player does not have the required key in their inventory.
2. The player decides to try picking the lock.
They have a lockpick in their inventory and a sufficient lockpicking skill.
The player selects the lockpicking action from the menu, and a progress bar appears, representing the lockpicking attempt.
3. After a few seconds, the lockpicking attempt succeeds, and the door is now unlocked.
The lock icon disappears, and the player can now open the door and access the room.
4. Later, the player finds a key that corresponds to the door lock they picked earlier.
They can now lock and unlock the door using the key, providing a more secure and convenient way of controlling access to the room.
5. As the player explores further, they encounter a portal storm monster trying to open a locked door but failing to do so.
Other monsters in the area try to break down the locked door, while NPCs with lockpicks and the required skill may attempt to pick the lock.

also, safety from portal storm surprises.
<!-- Add any other context (such as mock-ups, proof of concepts or screenshots) about the feature or bugfix here. -->


<!--README: Cataclysm: Dark Days Ahead is released under the Creative Commons Attribution ShareAlike 3.0 license.
The code and content of the game is free to use, modify, and redistribute for any purpose whatsoever.
By contributing to the project you agree to the term of the license and that any contribution you make will also be covered by the same license.
See http://creativecommons.org/licenses/by-sa/3.0/ for details. -->
