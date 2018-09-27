# Send_BuddyBuild_App_Unit_Tests_To_TestRail
This project accesses the BuddyBuild API, pulls the unit test results for the latest successful iOS build (specific to a branch &amp; environment) and then sends these results to the TestRail API, deleting any test cases &amp; runs currently present under a TestRail project, then creates a new test run, and cases &amp; run results.

How to Send BuddyBuild App Unit Tests To TestRail:

Requirements for this to work:
  1.	There must be an iOS app being built with Buddybuild with unit tests built into the code. The ‘tests’ section in the below image must not be blank.  
  2.	In TestRail, there must be a project, suite and group already created. Seen here:
  3.	For the script the required data must be configured in the code:
   a.	TestRail Password, TestRail Group Id, TestRail Project Id, TestRail Suite Id
   b.	BuddyBuild Password, BuddyBuild App Id
    -	I used tokens created by each site and an email for TestRail, as well as my testrail url
    -	I also configured print statements for the log using app name, etc.
    -	You will need to make these changes in the code
  4.	The script can then be called from terminal, cmd line or in a C.I. like Jenkins:
    pip install requests
    python send_buddybuild_tests_to_testrail.py $testRailPassword $buddyBuildPassword
      -	you could also pass in all the BuddyBuild / TestRail details as args
