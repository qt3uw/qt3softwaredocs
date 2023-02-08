# How To Publish Software to PyPI

We use the latest PEP standards for python packaging (pyproject.toml)
and Github Workflows to build and publish our various packages to PyPI.

PyPI is a convenient option to distribute versioned code for usage amongst
different researchers and groups.

As of this writing, the following instructions apply to these packages.

* qcsapphire
* nipiezojenapy
* qt3rfsynthcontrol
* pulseblaster
* qt3-utils

After some development has occurred in one of these repositories
and all branches have been merged to main, a new software version may be be ready for publication.

1. Update the version number in the project build file. Currently this is specified by "version" in `pyproject.toml`.
  * This can be done with a separate branch and PR, or can be committed directly to `main` if done by an admin.
2. Find the `Releases` tab on the repositories GitHub page.
3. Select `Draft a New Release`
4. Pull down the 'choose a tag' menu and create a new tag equal to the version number now found in `pyproject.toml`.
5. Fill in the release notes. The "Generate Release Notes" generally does a good job. And you may add any extra information you think is necessary
6. Select "set as a pre-release" if this is a "devX", "alphaX" or "betaX" version number
7. Select "set as the latest release" if this is a full version and GH asks
8. Click on the "Publish release" button.
9. Update the `pyproject.toml` "version" value to the next development cycle.
  * for example, bump "version" from "1.2.3" to "1.2.4.dev0"
  * this ensures clarity that development resumes after a release and there aren't any accidental versioning issues in local development
  * this can be done with a direct commit to `main` by an admin.

After step 8, Github should then build and publish the package to PyPI.
If you navigate to the "Actions" tab, you should see the release pipeline status and results.



# PyPI Ownership

Currently, the packages published on PyPI and the API tokens used
by Github Workflow are owned by G. Adam Cox ('gadamc@gmail.com').
Contact Adam to go through ownership transfer. You will need to create an
account on pypi.org, generate API tokens and transfer them to GitHub. This is
generally an easy process and may take only a few minutes.
