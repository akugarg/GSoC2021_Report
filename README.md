# Google Summer of Code 2021 Final Report
## Organization : [Aboutcode](https://www.aboutcode.org/)
##### Akanksha Garg <akanksha.garg2k@gmail.com>
##### [GSoC PROPOSAL](https://docs.google.com/document/d/1Dp0Hgk38RIMwITTiS-kqfikpkHRi2rjtkotA9CLw8j0/edit?usp=sharing)
## Project : Detect Unknown Licenses and Indirect License References in Scancode 
#### [Scancode-Toolkit](https://github.com/nexB/scancode-toolkit)
#### Project Board: https://github.com/nexB/scancode-toolkit/projects/9
### Description - 
- The main motive of this project was to improve license detection of unknown licenses and follow references to indirect license references in Scancode-TK
  #### Improvement in the License Data Model Definition
- Unknown Licenses are the ones which are matched to a license rule tagged with 'unknown' license key . Since these are some of the 'special' licenses , reporting     them with special attributes will provide more clarification. Now unknown licenses are tagged with a new flag **"is_unknown"** to identify them beyond
  just the naming convention of having "unknown" as part of their name. Rules that match at least one unknown license have a flag **"has_unknown"** set
  in the returned match results.

  | PR       | Status             |
  |-----------------------|-------------------|
  | [#2548](https://github.com/nexB/scancode-toolkit/pull/2548/commits/f1b8085b8a097fde2ce5c5bd02672efa3a07aa40) | ```MERGED```|
  
  #### Reporting known and Unknown licenses separately
- We considered having a separate section for of scan results to report 'unknown licenses' separately and not mixed with main license detection results. But after
  implementing a separate section for unknown ones ,it doesn't seem to be good idea to have currently. 
  
  | PR       | Status             |
  |-----------------------|-------------------|
  | [#2578](https://github.com/nexB/scancode-toolkit/pull/2578) | ```CLOSED ```|
  
  #### Follow License References to another file
- Some license references such as "see license in file LICENSE.txt" e.g. mentions to look for license details in another file are reported as unknown license references and we could instead follow the referenced file to find what was detected there. The approach was to use already contained attribute ```refrenced_filenmes``` in license RULE data files. Since this was a ```process_codebase``` step in scan plugin , it was needed that our API function should return ```refrenced_filenmes``` to keep track of these files corresponding to licenses detected. This was tracked in - 

  | PR       | Status             |
  |-----------------------|-------------------|
  | [#2632](https://github.com/nexB/scancode-toolkit/pull/2632) |```MERGED```|
  
-  The ```process_codebase``` step is tracked in - 
 
   | PR       | Status             |
   |-----------------------|-------------------|
   | [#2616](https://github.com/nexB/scancode-toolkit/pull/2616) | ```OPEN```|
 
#### Improve license detection of Unknown Licenses
- The approach was to use index of n-grams for detecting unknowns besides having our actual detection of "unknown" license rules. Firstly matches were filtered after running our normal procedure of license detection and the remaining spans are run through a automaton index containing n-grams from all regular license texts and rules. This is tracked in - 

   | PR       | Status             |
   |-----------------------|-------------------|
   | [#2592](https://github.com/nexB/scancode-toolkit/pull/2592) | ```OPEN```|
 
#### Addition of some new Licenses
- There were some licenses that were not present in Scancode-toolkit as for now. They have been added now. 

   | PR       | Status             |
   |-----------------------|-------------------|
   | [#2625](https://github.com/nexB/scancode-toolkit/pull/2625) | ```OPEN```|
 
  
