---
title: Release
has_children: false
nav_order: 7
---

# Release

For this project, the primary release artifact is the **Android application package (APK)**. It is automatically built and uploaded to GitHub Releases after a new tag is created following semantic versioning. This process takes place via GitHub Actions as a part of the CI/CD pipeline.

The pipeline uses the `softprops/action-gh-release` which is triggered whenever a new tag is pushed. 

## Current releases

Until the finalization of this project, versions from 1.0.0 to 1.0.7 were released, 1.0.7 being the final one. The additions from one version to another were mainly design and other small fixes, changes of tests or changes in the workflow file.

## Choice of the license

For the scope of this project, the **MIT License** was used. It is one of the most permissive open-source licenses available, permitting any person to use the software for any purpose, modify the source code, and distribute and commercialize the original or modified versions. When redistributing, the original MIT License must be included together with a copyright notice. The license does not guarantee any warranty, the original developers not being liable for fixing any bugs or issues that could arise. 

I chose this license because the project is developed for educational purposes, without the intention of making it a "real" product. If anybody would like to use or modify the code I strongly encourage them to, and I will not be liable for any issues that might appear. 

## Choice of the versioning schema

The **Semantic Versioning (SemVer)** schema was used for this project, as it is widely used for open-source projects and it is easily interpretable by both developers and other users/systems. Moreover, it works well with automation tools such as GitHub Actions which facilitates the release process.