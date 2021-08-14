# Google Summer of Code 2021 Final Report
## Organization : [Aboutcode](https://www.aboutcode.org/)
##### Akanksha Garg <akanksha.garg2k@gmail.com>
##### [GSoC PROPOSAL](https://docs.google.com/document/d/1Dp0Hgk38RIMwITTiS-kqfikpkHRi2rjtkotA9CLw8j0/edit?usp=sharing)
## Project : Detect Unknown Licenses and Indirect License References in Scancode 
#### [Scancode-Toolkit](https://github.com/nexB/scancode-toolkit)
#### Project Board: https://github.com/nexB/scancode-toolkit/projects/9
### Description - 
- The main motive of this project was to improve license detection of unknown licenses and follow references to indirect license references in Scancode-TK
  #### Improvement the License Data Model Definition
- Unknown Licenses are the ones which are matched to a license rule tagged with 'unknown' license key . Since these are some of the 'special' licenses , reporting     them with special attributes will provide more clarification. Now unknown licenses are tagged with a new flag **"is_unknown"** to identify them beyond
  just the naming convention of having "unknown" as part of their name. Rules that match at least one unknown license have a flag **"has_unknown"** set
  in the returned match results.

  | PR       | Status             |
  |-----------------------|-------------------|
  | [#2548](https://github.com/nexB/scancode-toolkit/pull/2548/commits/f1b8085b8a097fde2ce5c5bd02672efa3a07aa40) | ![Merged](https://i.imgur.com/YnDnRzm.jpg) |
