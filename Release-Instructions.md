# Release Instructions

Stage does not currently have an automated release system. These release instructions have been created in order to avoid mistakes while making a release.

## Instructions

### Build the server app package
1. Pull the latest stage-server repository changes and ensure everything is up-to-date by running: `git pull; git submodule foreach --recursive "(git checkout master; git pull)"; git status`
1. Open MATLAB
1. Change directory to the root stage-server submodule directory within the stage repository
1. Add the lib and src directory and their child directories to the MATLAB path
1. Open Stage Server.prj
1. Click "Refresh dependencies"
1. Close the project
1. Edit `stageui.app.App` and make sure the version matches the next release version number
1. Package the app by running: `package`

### Build the toolbox package
1. Pull the latest stage repository changes and ensure everything is up-to-date by running: `git pull; git submodule foreach --recursive "(git checkout master; git pull)"; git status`
1. Open MATLAB
1. Change directory to the root stage directory
1. Generate the documentation from the docs repo by running: `site`
1. Replace src/main/resources/docs with target/site
1. Add the lib and src directory and their child directories to the MATLAB path
1. Edit `stage.app.App` and make sure the version matches the next release version number (*this should generally be the same number used while building the server app*)
1. Package the toolbox by running: `package`

The releasable toolbox (Stage.mltbx) is now under the target directory.

### Create a new release on GitHub
1. Go to https://github.com/Stage-VSS/stage/releases
1. Click "Draft a new release"
1. Enter the tag version as the Stage version number being release (e.g. 2.0.2.1)
1. Enter the release title in the format "STAGE_VERSION (MAJOR.MINOR-DEV_STAGE.REV) x64" (e.g. 2.0.2.1 (2.0-rc1) x64). The third position of the full STAGE_VERSION indicates the DEV_STAGE: 0 = alpha, 1 = beta, 2 = release candidate, 3 = release. The forth position indicates the REV.
1. Enter the release notes
1. Attach the Stage.mltbx file
1. Mark the build as pre-release if the dev stage is alpha, beta, or release candidate

### Update the Stage-VSS website
1. Pull the latest stage-vss.github.io repository changes and ensure everything is up-to-date by running: `git pull; git submodule foreach --recursive "(git checkout master; git pull)"; git status`
1. Open the \_config.yml file
1. Replace the "version" property value with the new Stage version number
1. Commit and push the change to GitHub
