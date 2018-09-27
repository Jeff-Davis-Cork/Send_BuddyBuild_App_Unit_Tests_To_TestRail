# Send_BuddyBuild_App_Unit_Tests_To_TestRail
This project accesses the BuddyBuild API, pulls the unit test results for the latest successful iOS build (specific to a branch &amp; environment) and then sends these results to the TestRail API, deleting any test cases &amp; runs currently present under a TestRail project, then creates a new test run, and cases &amp; run results.
