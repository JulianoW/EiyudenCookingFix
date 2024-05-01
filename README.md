# EiyudenCookingFix
Mod that fixes cooking and makes it fun again!

# Technical Details
As of version 1.04, there are a couple of issues with the cooking battle minigame. They all stem from a single design decision in the scoring system:
* The game has code to penalize you if you cook a dish in the wrong round, i.e., cooking a dessert for a main dish. 

With that in mind, we can examine the issues:
1. The round type is never initialized, and defaults to 0: Appetizer. This means all rounds are scored as if they are an Appetizer round. Another way to look at this is: Appetizers always get full marks, Main Dishes and Desserts ALWAYS get penalized 50%.
2. If you look at the cooking battle line-up, you will notice that the judges completely ignore the round type. They will keep making appetizers for desserts, or main dishes for desserts, main dishes for appetizers, etc. And they never stop doing that.
   
Knowing this, it makes you wonder if maybe they decided to remove the round penalty but messed up the implementation? If you look at the logic here, it's actually very similar to Suikoden 2. Even the judge taste categories are exactly the same!

Anyway, what this patch does is simply change every dish to be an appetizer, so that they always get full scores based on the other scoring criteria. This means you can finally cook ANY dish and get an appropriate score, and your opponents will actually put up more of a fight, now!

See wiki for more information on Cooking Battle mechanics:
https://eiyuden.wiki.gg/wiki/Cooking_Battle

# Directions
This patch is intended to work **ONLY** on **Steam build 14133848**. This seems to be the equivalent of console 1.04. It is the current update as of 4/30/24. **DO NOT USE THIS WITH FUTURE PATCHES.** Not tested on other PC versions. Test at your own risk.

1. Close the game if it is running
2. Go to your game directory, and browse to: \EiyudenChronicle_Data\StreamingAssets\aa\StandaloneWindows64
3. Back up the file named `dc45330cf35da75eac71f243c0f8c2fd.bundle`. For example, rename it to `dc45330cf35da75eac71f243c0f8c2fd.bundle.bak`.
4. Copy the `dc45330cf35da75eac71f243c0f8c2fd.bundle` file from here and place it in that folder.

To uninstall, simply remove the file and restore your original, or force Steam to update your files.

Enjoy!
