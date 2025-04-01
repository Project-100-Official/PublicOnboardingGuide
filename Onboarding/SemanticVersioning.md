# Semantic Versioning

## Summary

Link to page: https://semver.org/

Given a version number `MAJOR.MINOR.PATCH` increment the:

1. `MAJOR` version when you make incompatible production changes
2. `MINOR` version when you add functionality in a backward compatible manner
3. `PATCH` version when you make backward compatible bug fixes

### Semantic Versioning Specification

1. A normal version number MUST take the form `X.Y.Z` where X, Y, and Z are
non-negative integers and MUST NOT contain leading zeroes. X is the major version,
Y is the minor version, and Z is the patch version. Each element MUST increase
numerically. For instance: `1.9.0` > `1.10.0` > `1.11.0`.
2. Once a versioned package (git tagged `stable` branch) has been released, the
contents of that version MUST NOT be modified. Any modifications must be released
to a new version.
3. Major version zero (`0.y.z`) is for initial development. Anything may change
at any time. The “production” code should not be considered `stable`.
4. Version `1.0.0` defines the public launch production. The way in which the
version number is incremented after this release is dependent on how it changes.
5. Patch version Z (`x.y.Z` x > 0) MUST be incremented if only backward compatible
bug fixes are introduced. A bug fix is defined as an internal change that fixes
incorrect behavior.
6. Minor version Y (`x.Y.z` x > 0) MUST be incremented if new, backward compatible
functionality is introduced to the public application. It MUST be incremented if
any public application functionality is marked as deprecated. It MAY be
incremented if substantial new functionality or improvements are introduced
within the private code. It may include patch-level changes. Patch version MUST
be reset to 0 when minor version is incremented.
7. Major version X (`X.y.z` X > 0) MUST be incremented if any backward
compatibility changes are introduced to the public application. It may also
include minor- and patch-level changes. Patch and minor versions MUST be reset
to 0 when major version is incremented.
8. A pre-release version may be denoted by appending a hyphen and a series of dot
separated identifiers immediately following the patch version. Identifiers must
comprise only ASCII alphanumeric characters and hyphens [0-9, A-Z, a-z].
Identifiers must not be empty. Numeric identifiers must not include leading zeroes.
Pre-release versions have a lower precedence than the associated normal version.
A pre-release version indicates that the version is unstable and might not
satisfy the intended compatibility requirements as denoted by its associated
normal version. Examples: `1.0.0-alpha`, `1.0.0-alpha.1`, `1.0.0-0.3.7`,
`1.0.0-x.7.z.92`, `1.0.0-x-y-z.—`.
9. Precedence refers to how versions are compared to each other when ordered.
    1. Precedence MUST be calculated by separating the version into major, minor,
    patch and pre-release identifiers in that order.
    2. Precedence is determined by the first difference when comparing each of
    these identifiers from left to right as follows: Major, minor, and patch
    versions are always compared numerically.
        
        Example: `1.0.0` < `2.0.0` < `2.1.0` < `2.1.1`.
        
    3. When major, minor, and patch are equal, a pre-release version has lower
    precedence than a normal version:
        
        Example: `1.0.0-alpha` < `1.0.0`.
        
    4. Precedence for two pre-release versions with the same major, minor, and
    patch version MUST be determined by comparing each dot separated identifier
    from left to right until a difference is found as follows:
        1. Identifiers consisting of only digits are compared numerically.
        2. Identifiers with letters or hyphens are compared lexically in ASCII
        sort order.
        3. Numeric identifiers always have lower precedence than non-numeric
        identifiers.
        4. A larger set of pre-release fields has a higher precedence than a
        smaller set, if all of the preceding identifiers are equal.
    
    Example: `1.0.0-alpha` < `1.0.0-alpha.1` < `1.0.0-alpha.beta` < `1.0.0-beta`
    < `1.0.0-beta.2` < `1.0.0-beta.11` < `1.0.0-rc.1` < `1.0.0`.
    
---

Questions about the repository, including merge conflicts, how-to's, initial
setup, etc. should be sent to [@DistractedGames](https://discordapp.com/users/358030688785793026).

Questions about feature design, assets, and general implementation should be sent
to [@Vortex](https://discordapp.com/users/602611579262992401).
