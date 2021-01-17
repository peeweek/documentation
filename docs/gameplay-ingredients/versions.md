# Version Compatibility

Gameplay Ingredients have been around for some time and has changed a little since the beginning. Because unity is evolving and the ecosystem of packages around evolves as well, compatibility rules have arisen.

## Compatibility and Version Numbers

Gameplay Ingredients is using [semver](https://semver.org/)-like version numbers for package compatibility with Unity and [OpenUPM](https://openupm.com/packages/), however, the version numbers have extra meaning when it comes to compatibility with Unity.

### Rule #1: the Major.Minor version

The MAJ.MIN version (eg: 2020.2) determines the minimum Unity version compatible with the given package. So, 2019.3.x packages, will be compatible with 2019.3 and newer versions.

### Rule #2 : Check the Table for Forward Compatibility

Regarding forward compatibility, some package can be compatible with multiple forward versions. This is the case for instance for LTS versions. However, sometimes, we do not have the ability to check all versions and forward compatibility will not be assured at all costs. In this table, you will find the latest compatible package version for each Unity Version

| Unity Version  | Gameplay Ingredients Version | Comments or Details                                          |
| -------------- | ---------------------------- | ------------------------------------------------------------ |
| **2020.2 LTS** | 2020.2.x                     | Breaking Change : Open UPM Install in 2020.2.0               |
| 2020.1         | 2019.3.7                     |                                                              |
| **2019.4 LTS** | 2019.3.7                     |                                                              |
| 2019.3         | 2019.3.7                     | UI Changes for Unity Skin overhaul                           |
| 2019.2         | 2019.1.2                     |                                                              |
| 2019.1         | 2019.1.2                     | Fixed package to run on 2019.1, not compatible anymore with 2018. |
| **2018.4 LTS** | 2018.3.0                     |                                                              |
| 2018.3         | 2018.3.0                     |                                                              |

# Major Breaking Changes

Here's a recap of all major breaking changes and how to handle them if when you upgrade.

### External Dependency Changes (2019.3.7 > 2020.2.0)

This change involves using [Package Manager Scoped Registries](https://docs.unity3d.com/2020.1/Documentation/Manual/upm-scoped.html) in your project in order to reference `com.dbrizov` scope from Open UPM registry. Starting 2020.2.0, [NaughtyAttributes](https://openupm.com/packages/com.dbrizov.naughtyattributes/) code have been removed from Gameplay Ingredients and is now a package dependency.

### Changed Discover Assets to reference multiple Scenes / SceneSetups (2019.1.1 > 2019.1.2)

In this change, the target scene field was changed for two arrays, one for scenes, the other for scene setups. You will have to re-enter manually the fields.

### Removed Counts from OnTriggerEvent (2018.3.0 > 2019.1.0)

In this change, counts were removed from OnTriggerEvent, please use NTimesLogic in order to perform the count check.