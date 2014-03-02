Contributors
audience: project manager (track who's contributing and how much), contributors (track contributions from others)
data: contributors, their commits, and information on commits (time, size of changes)
- GET /repos/:owner/:repo/git/commits/:sha
commit surge: the graph for that contributor would have a huge spike and it would be hard to see the time course of the previous commits
- fix: change the scale to log

Commits Activity
audience: project manager (track development of overall project), contributors, users (see development of project)
data: number of commits for each day
- GET /repos/:owner/:repo/git/commits/:sha
commit surge: the graph would have a huge spike and it would be hard to see the time course of the previous commits
- fix: change the scale to log, scale adjusts to max data point in frame

Code Frequency
audience: project manager, any other interested persons in how the volume of code is change over time
data: additions and deletions for each day (calculated from commit data for each day)
- GET /repos/:owner/:repo/git/commits/:sha
commit surge: the graph would have a huge spike and it would be hard to see the time course of the previous commits
- fix: change the scale to log, scale adjusts to max data point in frame

Punch Card
audience: project manager (track development of overall project), contributors, users (see development of project)
data: number of commits for each day
- GET /repos/:owner/:repo/git/commits/:sha
commit surge: the circles might get too big and overlap
- fix: normalize the radius/area of circle to the largest number of commit/day 

Pulse
audience: project manager (see current and resolved issues and pushes), contributors (see what needs to be fixed), users (see current issues and overview of current activity)
data: time line data for issues opened, closed, push requests, merged
- GET /repos/:owner/:repo/pulls
- GET /repos/:owner/:repo/git/commits/:sha
commit surge: not too much problems. The older stories might get pushed out of view before they are read
- fix: be able to scroll through individual time lines 

Questions
1. The interaction allows us to look through different time periods and to obtain more details on a commit through hovering. If a static graph tried to offer the same information, it would get crowded very easily

2. If many users join and push commits at the same time, because each commit joins the main branch at a right angle, the graph at the point when the many pushes are made will be very crowded and hard to distinguish which contributor pushed when.
- fix: use a stream-like feature that merges nearby commits. On hover, the stream would reveal more deails about the 