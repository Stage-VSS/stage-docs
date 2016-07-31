Stage does not currently have an automated release system. These release instructions have been created in order to avoid mistakes while making a release.

## Instructions

### Build the server app package
1. Pull the latest stage2-server repository changes and ensure everything is up-to-date by running: `git pull; git submodule foreach --recursive "(git checkout master; git pull)"; git status`
1. Open MATLAB
1. Change directory to the root stage2-server submodule directory within the stage2 repository
1. Add the lib and src directory and their child directories to the MATLAB path
1. Open Stage Server.prj
1. Click "Refresh dependencies"
1. Close the project
1. Edit `stageui.app.App` and make sure the version matches the next release version number
1. Package the app by running: `package`

### Build the toolbox package
1. Pull the latest stage2 repository changes and ensure everything is up-to-date by running: `git pull; git submodule foreach --recursive "(git checkout master; git pull)"; git status`
1. Open MATLAB
1. Change directory to the root stage2 directory
1. Generate the documentation from the wiki by running: `site`
1. Replace src/main/resources/docs with target/site
1. Add the lib and src directory and their child directories to the MATLAB path
1. Edit `stage.app.App` and make sure the version matches the next release version number (*this should generally be the same number used while building the server app*)
1. Package the toolbox by running: `package`

The releasable toolbox (Stage.mltbx) is now under the target directory.
