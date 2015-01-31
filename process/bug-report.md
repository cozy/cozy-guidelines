## Bug report

A bug can be reported via several channels: Github, forum, Cozy Cloud 
contact email or directly from a friend. Here is the process to
follow when it occurs:

1. Github issue creation on the right repository
    * Answer to the user with a link to the issue.
2. Developer assignment of the ticket + adding label `in progress` to the ticket
3. Add a test to the test suite of the repository
4. Open a Pull Request
5. Once a developer is statisfied with his development, he informs the 
   Technical Referant of the repository for merging by tagging the PR with `good to merge`.
   (discussion on the PR).
6. The product Owner of the repository is requested for testing the fix by 
   tagging the issue `QA` (discussion is made on the issue).
7. If the PO finds something wrong, he changes the label `QA` to `retake`.
8. If everything is ok, the change is published 
9. The PO informs the user about the bug fix and asks for a test.
10. If everything is ok, the PO closes the issue else the process goes back to step 3.
