# How to Contribute

Stage is an open source project and anyone is welcome to contribute. However, please make sure your changes are relevant to all users to avoid bloating the common code. If you're unsure, create an issue to discuss. Also, please abide by the [style guide](Style-Guide.md).

## Instructions

### One-time Setup
1. Fork the [stage](https://github.com/Stage-VSS/stage) repository
1. Clone your personal fork to your computer:  
`git clone https://github.com/YOUR_USERNAME/stage.git`
1. Add a remote repository:  
`git remote add upstream https://github.com/Stage-VSS/stage.git`

### General Workflow
1. Sync your repo:  
`git pull upstream master`
1. Create a topic branch:  
`git checkout -b TOPIC_BRANCH_NAME master`
1. Make changes and commit:  
`git commit -am "A description of my changes."` or `git commit -am "[fixed ISSUE_NUM] description"` (if fixing an issue tracked in GitHub)
1. Push to GitHub:  
`git push origin TOPIC_BRANCH_NAME`
1. Submit a pull request
