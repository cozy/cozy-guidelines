## Bug report

A bug can reported via several channels: Github, forum, Cozy Cloud 
contact email or directly from a friend. Here is the process to
follow when it occurs

1. Github ticket creation on the right repository
2. Developer assignment of the ticket + adding label `in progress` to the ticket
3. Add a test to the test suite of the repository
4. Open a Pull Request
5. Once a developer is statisfied with his development he informs the right people
    * Technical Referant of the repository for merging 
      (discussion on the PR, mention the RT in the PR).
    * Product Owner of the repository for closing the issue 
      (discussion is made on the issue, add the label `QA` to the issue).
6. if the PO finds something wrong, he changes the label `QA` to `retake`.
7. If everything is ok, the TR merges the pull request and the PO closes the issue.
