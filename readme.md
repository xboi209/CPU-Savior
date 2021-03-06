CPU Savior
=========
CPU Savior is a plugin that will introduce a 1 millisecond delay every time StarCraft calls GetTickCount. Since StarCraft does this so
often with no delay, it results in 100% CPU usage. With this plugin, CPU usage is greatly reduced.

Note: Source code for v1.6 is not available.

Compiling
=========
A C++98 compliant compiler with WinAPI available should be able to compile this project.

Risks
=========
Modifies the Import Address Table(IAT) in memory. Does not modify StarCraft code.

History
=========
Version				| Description
------------------- | -------------
v1.0 (Feb 05 2008)	| First and final release, for 1.15.2.
v1.2 (Mar 27 2008)  | Well I guess 1.0 wasn't the final release after all :). Added code to Sleep during Battle.Net dialog loop so the bnet lobby doesn't consume 100% CPU. Hard-coded storm.dll offset, if your storm.dll is relocated this will likely crash.
v1.3 (Apr 10 2008)	| Fix an access violation when running on a system with DEP enabled for all programs.
v1.4 (Jun 02 2008)	| Sleep only on calls from game loop, menu and bnet instead of every call. Hopefully this should fix the "mouse lag" reported by some users, and also allows replays to run at 16x without a problem. CPU usage may be slightly higher than previous versions however, but still nowhere near 100%.
v1.5 (Sep 14 2008)	| Updated offsets for 1.15.3 patch.
v1.6 (Jan 10 2010)	| Updated offsets for 1.16.1 patch. Note, 1.16.1 contains CPU Throttling which has a similar effect to CPU Savior, however some people report that CPU Throttling causes small mouse lag, likely related to no timeBeginPeriod call. Be sure to disable CPU Throttling if using this plugin with 1.16.1.

License
=========
CPU Savior is licensed under the [zLib license](https://github.com/xboi209/CPU-Savior/blob/master/LICENSE.md).
