---
# (Required) Ensure all values are filled up
name: "Move a post from DM"
status: Active
priority: Normal
folder: Move Threads
authors: "@yasserfaraazkhan"
team_ownership: 
- ICU
priority_p1_to_p4: P2 - Core Functions (Do core functions work?)

# (Optional)
location: null
component: null
tags: []
labels: []
tested_by_contributor: null

# (Optional) Test type and tools
cypress: null
detox: null
mmctl: null
playwright: null
rainforest: []
manual_test_environments: []

# Do not change
id: null
key: null
created_on: null
last_updated: null
case_hashed: null
steps_hashed: null
---

**Step 1**

Scenario 1: Move root post from DM

Test Setup:

1. Feature flag `moveThreadsEnabled` should be enabled.
2. Enable `Enable Moving Threads From Direct Message Channels` option from the System Console > Move thread.
3. Have 2 users example: User A and User B.

Steps:

1. Log into mattermost with User A.
2. Post a message in the DM channel with User B.
3. Hover on the post and click on the dot menu to see message actions.
4. Click on `Move Thread` option.
5. Verify a pop up with `Move thread` header appears.
6. Select the channel from `Select channel or people` dropdown.
7. Click on `Move` button.
8. Verify the post appears in the new channel.
9. Navigate to previous channel from where the thread was moved.
10. Verify a system message `A thread with N messages has been moved: http://<instance-name>/<team-name>/pl/<channel-id>` is shown.

Scenario 2: Should not be able to Move root post from DM

Test Setup:

1. Feature flag `moveThreadsEnabled` should be enabled.
2. Disable `Enable Moving Threads From Direct Message Channels` option from the System Console > Move thread.
3. Have 2 users example: User A and User B.

Steps:

1. Log into mattermost with User A.
2. Post a message in the DM channel with User B.
3. Hover on the post and click on the dot menu to see message actions.
4. `Move Thread` option should not be shown to the user.