# gauge_concept_search
Small gauge project to show that concepts are found outside of specs folder

According to the [gauge documentation], concepts are found in `<project_root>/specs` and all underlying folders.  
It seems however, that this is not actually limited to the `specs` folder, but searches all of the `<project_root>`.

As example there is a duplicated concept in this project, once in `<project_root>/specs` and once in `<project_root>/someOtherFolder`

To test that both are found run the following commands:
```shell
npm install
npm run gauge
```
The following error should appear:
```
[ParseError] <project_root>/specs/Concept.cpt:1 Duplicate concept definition found => 'Search <term> on Wikipedia'
[ParseError] <project_root>/someOtherFolder/Concept.cpt:1 Duplicate concept definition found => 'Search <term> on Wikipedia'
```
If one of the concepts is deleted or the file type is changed the test works.

Also note that the npm script runs `gauge run specs` and in the `default.properties` file the `gauge_specs_dir` property is set to `specs`

[gauge documentation]: https://docs.gauge.org/writing-specifications.html?os=macos&language=javascript&ide=vscode#concepts